---
markmap:
  initialExpandLevel: 2
---

# MUNI — Computer Science

## Tuần 1 · 26/10–01/11/2026

### Big-O & Algorithm Analysis
- **Input size — n**: số phần tử hoặc kích thước đầu vào
- **Time complexity**: số phép toán tăng thế nào theo n; không phải thời gian tính bằng giây
- **Big-O**: cận trên tiệm cận; khi so sánh thuật toán trong ghi chú này, dùng mức tăng trưởng chặt thông dụng
  - O(1): constant — số thao tác không tăng theo n
  - O(log n): logarithmic — mỗi bước giảm phạm vi theo một tỉ lệ cố định
  - O(n): linear — duyệt số phần tử tỉ lệ với n
  - O(n log n): thường gặp ở sorting chia để trị cân bằng
  - O(n²): quadratic — thường gặp khi xét các cặp phần tử
  - Thứ tự tăng: O(1) → O(log n) → O(n) → O(n log n) → O(n²)
- **Drop constants** — bỏ hệ số hằng
  - 2n, 5n + 3 → O(n)
  - `i += 2` vẫn chạy khoảng n/2 lần → O(n)
- **Dominant term** — giữ số hạng tăng nhanh nhất
  - n² + 10n + 5 → O(n²)
  - n + log n → O(n)
- **Sequential loops** — vòng lặp liên tiếp: cộng chi phí
  - Một vòng n bước, tiếp theo một vòng n bước → 2n → O(n)
  - Một vòng n bước, tiếp theo một vòng log n bước → O(n)
- **Nested loops** — vòng lặp lồng nhau: đếm tổng số lần chạy thân trong
  - Hai vòng độc lập, mỗi vòng n bước → O(n²)
  - Vòng ngoài n lần, vòng trong log n lần → O(n log n)
  - Không mặc định mọi cặp vòng lặp lồng nhau đều O(n²)
- **Logarithmic loops**
  - `for (let i = 1; i < n; i *= 2)` → O(log n)
  - `while (n > 1) { n = Math.floor(n / 2); }` → O(log n)
  - Logarithm: số lần nhân/chia theo cùng một cơ số; với Big-O, cơ số cố định lớn hơn 1 chỉ khác hệ số hằng
- **Best / Average / Worst case**
  - Best: đầu vào thuận lợi nhất
  - Average: kỳ vọng theo giả định phân bố đầu vào
  - Worst: đầu vào tốn nhiều thao tác nhất với cùng n
  - Big-O không đồng nghĩa với worst-case; phải xác định trường hợp đang xét

### Searching Algorithms
- **Linear Search** — tìm kiếm tuyến tính
  - Kiểm tra lần lượt đến khi thấy target hoặc hết mảng
  - Không cần mảng đã sắp xếp
  - Best O(1); worst O(n)
  - Unsuccessful search trên n phần tử: n lần so sánh phần tử với target
  - Tracing: ghi vị trí đã kiểm tra, giá trị và kết quả
- **Binary Search** — tìm kiếm nhị phân
  - Điều kiện: mảng đã sắp xếp; phiên bản ở đây dùng random access trên array
  - Khởi tạo `low = 0`, `high = n - 1`
  - Lặp khi `low <= high`
    - `mid = Math.floor((low + high) / 2)`
    - Nếu `a[mid] === target`: tìm thấy
    - Nếu `a[mid] < target`: `low = mid + 1`
    - Nếu `a[mid] > target`: `high = mid - 1`
  - Khi `low > high`: không tìm thấy
  - Best O(1); worst O(log n)
  - Mỗi bước loại bỏ khoảng một nửa phạm vi còn lại
  - Tracing nên ghi `low`, `high`, `mid`, `a[mid]`
- **Comparison counting**
  - Phân biệt một lần kiểm tra phần tử giữa với số phép `===`, `<`, `>` thực thi trong code
  - Đọc quy ước của đề trước khi đếm
  - Không đếm điều kiện `low <= high` thành một lần so sánh target với phần tử
  - Sau khi phạm vi rỗng, không có lần kiểm tra phần tử bổ sung

### Bubble Sort
- **Nguyên lý**: so sánh hai phần tử kề nhau; swap nếu sai thứ tự
- **Ascending order**: đổi khi `a[j] > a[j + 1]`
- Một pass từ trái sang phải đẩy phần tử lớn nhất của phần chưa sắp xếp về cuối
- Sau mỗi pass, có thể giảm phạm vi bên phải cần duyệt
- **Tracing**: thực hiện đủ các adjacent comparisons của pass; không nhầm một swap với một pass
- **Early termination**: nếu một pass không có swap, kết thúc
- **Time**
  - Best O(n) với early termination
  - Best O(n²) với phiên bản luôn chạy đủ các vòng
  - Average / Worst O(n²)
- **Auxiliary space**: O(1) với phiên bản swap tại chỗ
- **Stable** nếu chỉ swap khi lớn hơn nghiêm ngặt
- Ví dụ pass đầu: `[3, 1, 2]` → `[1, 3, 2]` → `[1, 2, 3]`

### Insertion Sort
- **Nguyên lý**: giữ prefix đã sắp xếp, chèn phần tử tiếp theo vào đúng vị trí
- Với mỗi `i` từ 1 đến n − 1
  - Lưu `key = a[i]`; đặt `j = i - 1`
  - Khi `j >= 0` và `a[j] > key`: dịch `a[j]` sang phải, giảm j
  - Đặt key tại `a[j + 1]`
- **Shift**: dịch một phần tử; khác với một comparison và khác với swap
- Khi đếm comparisons, xét cả phép so sánh thất bại cuối nếu code thực thi nó
- Nếu `j < 0`, short-circuit có thể ngăn phép so sánh phần tử với key
- **Time**: best O(n), average / worst O(n²)
- **Auxiliary space**: O(1)
- **Stable** với điều kiện dịch `a[j] > key`, giữ nguyên thứ tự các giá trị bằng nhau
- Ví dụ: `[3, 1, 2]` → chèn 1: `[1, 3, 2]` → chèn 2: `[1, 2, 3]`
- **So với Bubble Sort**
  - Bubble: swap các cặp kề nhau, cố định dần suffix
  - Insertion: shift để chèn key vào sorted prefix

### Merge Sort
- **Divide and Conquer** — chia để trị
  - Split: chia mảng thành hai phần
  - Recursion: sắp xếp từng phần
  - Merge: ghép hai phần đã sắp xếp
- **Base case**: mảng có không quá một phần tử
- **Merge two sorted arrays**
  - Hai con trỏ, mỗi con trỏ đứng ở phần tử chưa lấy đầu tiên của một mảng
  - So sánh hai giá trị đang trỏ; lấy giá trị nhỏ hơn
  - Một bên hết: nối toàn bộ phần còn lại bên kia
  - Tổng độ dài m + k → merge tốn O(m + k)
- **Comparisons**
  - Chỉ đếm so sánh element-to-element nếu đề yêu cầu như vậy
  - Khi một bên hết, nối phần dư không cần so sánh hai phần tử nữa
  - Ví dụ `[1, 4]` và `[2, 3]`: so 1–2, 4–2, 4–3 → 3 comparisons
- **Time**: best / average / worst O(n log n) với phiên bản chuẩn đã học
  - Khoảng log n tầng; tổng công việc merge mỗi tầng O(n)
- **Auxiliary space**: O(n) cho phiên bản array chuẩn dùng buffer
  - Recursion stack O(log n); tổng phụ trợ vẫn O(n)
- **Stable** nếu khi bằng nhau, lấy phần tử bên trái trước
- Phiên bản chuẩn dùng buffer không phải in-place

### Quick Sort — Lomuto Partition
- **Nguyên lý**: partition quanh pivot, sau đó đệ quy hai phía
- **Quy ước ghi chú**: pivot ở cuối, partition bằng điều kiện `a[j] <= pivot`
  - Một phiên bản dùng `< pivot` có thể tạo tracing khác; luôn theo code đề
- **Lomuto partition trên đoạn low..high**
  - `pivot = a[high]`; `i = low - 1`
  - Duyệt `j = low` đến `high - 1`
  - Nếu `a[j] <= pivot`: tăng i, swap `a[i]` và `a[j]`
  - Kết thúc vòng: swap `a[i + 1]` và `a[high]`
  - Trả về `p = i + 1`
- **Sau partition**
  - Pivot ở vị trí cuối cùng đúng của nó
  - Bên trái ≤ pivot, bên phải > pivot theo quy ước trên
  - Hai phía chưa nhất thiết được sắp xếp
  - Recursive calls: `quickSort(low, p - 1)` và `quickSort(p + 1, high)`
  - Không đưa pivot trở lại hai đoạn đệ quy
- **Base case**: `low >= high` → dừng, không gọi partition
- **Tracing ví dụ**: `[3, 1, 2]`, pivot 2
  - 3 > 2 → bỏ qua
  - 1 ≤ 2 → đưa 1 về trái: `[1, 3, 2]`
  - Final pivot swap → `[1, 2, 3]`, p = 1
- **Duplicate values**
  - `<= pivot` đưa phần tử bằng pivot sang trái
  - Nhiều giá trị trùng có thể tạo partition mất cân bằng với Lomuto hai phía
- **Balanced partition**: hai phần gần bằng nhau → khoảng log n tầng
- **Unbalanced partition**: kích thước 0 và n − 1 lặp lại → khoảng n tầng
- **Time**
  - Một lần partition đoạn k phần tử: O(k)
  - Best / Average O(n log n)
  - Worst O(n²)
  - Pivot cuối với mảng đã tăng/giảm có thể gây worst-case
  - Random pivot giảm nguy cơ gặp chuỗi pivot xấu; không loại bỏ worst-case
- **Auxiliary space — phiên bản đệ quy thông thường đã học**
  - Partition tại chỗ: O(1) bộ nhớ phụ
  - Stack: average O(log n), worst O(n)
  - Không nhầm O(n log n) / O(n²) của time thành space
- **In-place**: partition không cần buffer tỉ lệ n; vẫn phải tính recursion stack khi hỏi tổng bộ nhớ phụ
- **Không stable** với Lomuto thông thường do swap có thể đảo thứ tự các phần tử bằng nhau

### So sánh Sorting
- **Bubble**: adjacent swaps; best O(n) nếu early termination; average/worst O(n²); space O(1)
- **Insertion**: chèn vào sorted prefix; best O(n); average/worst O(n²); space O(1)
- **Merge**: split → recursion → merge; mọi trường hợp chuẩn O(n log n); space O(n)
- **Quick**: partition → recursion; best/average O(n log n), worst O(n²); stack average O(log n), worst O(n)
- **Stable sorting**: giữ thứ tự tương đối ban đầu của các phần tử có cùng key
  - Bubble, Insertion, Merge: stable với điều kiện triển khai đã nêu
  - Quick Lomuto: thường không stable
- **Time vs Space**
  - Time: số công việc thực thi
  - Auxiliary space: bộ nhớ thêm ngoài dữ liệu đầu vào, gồm stack nếu có
- **Recursion**
  - Cả Quick Sort và Merge Sort trong phiên bản đã học đều đệ quy
  - Base case kết thúc nhánh, không thực hiện thêm partition/split
