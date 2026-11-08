---
markmap:
  initialExpandLevel: 2
---

# MUNI — Mathematics

## Tuần 1 · Học từ 24/10, tổng ôn 01/11/2026

### Mathematical Notation — Ký hiệu toán
- **Number sets — các tập số**
  - ℕ: số tự nhiên; kiểm tra quy ước của đề có bao gồm 0 không
  - ℤ: số nguyên, ví dụ −2, −1, 0, 1, 2
  - ℚ: số hữu tỉ, viết được a/b với a, b nguyên và b ≠ 0
  - ℝ: số thực, gồm số hữu tỉ và vô tỉ
  - ℕ ⊆ ℤ ⊆ ℚ ⊆ ℝ
- **Membership — thuộc**
  - `x ∈ A`: x là một phần tử của A
  - `x ∉ A`: x không là phần tử của A
- **Subset — tập con**
  - `B ⊆ A`: mọi phần tử của B đều thuộc A; cho phép B = A
  - `B ⊊ A`: B là tập con thực sự của A, B ≠ A
- **Empty set — tập rỗng**: ∅, không có phần tử
- **Cardinality**: `|A|` là số phần tử của tập hữu hạn A
- **Quantifiers — lượng từ ở mức nhận diện**
  - `∀`: for all — với mọi
  - `∃`: there exists — tồn tại ít nhất một
  - Ví dụ `∀x ∈ A, x > 0`: mọi phần tử của A đều dương
- **Set-builder notation**: mô tả tập bằng điều kiện
  - `{x ∈ ℤ | −1 ≤ x < 3} = {−1, 0, 1, 2}`
  - Phân biệt `<` và `≤`; kiểm tra có lấy hai đầu khoảng không

### Sets — Tập hợp
- Tập hợp là một collection các phần tử phân biệt
- **Không có thứ tự**: `{1, 2} = {2, 1}`
- **Không tính trùng**: `{1, 1, 2} = {1, 2}`, cardinality là 2
- Phần tử có thể là số, ordered pair hoặc một tập khác
- **Nested sets**: tập nằm trong tập
  - `{1, {2, 3}}` có 2 phần tử: số 1 và tập `{2, 3}`
  - Không tự mở tập con ra để đếm các phần tử bên trong

### Set Operations — Phép toán tập hợp
- Dùng ví dụ `A = {1, 2, 3}`, `B = {3, 4}`
- **Union — hợp: A ∪ B**
  - Thuộc A hoặc B, có thể thuộc cả hai
  - Ví dụ `{1, 2, 3, 4}`
  - Không lặp lại phần tử chung
- **Intersection — giao: A ∩ B**
  - Thuộc cả A và B
  - Ví dụ `{3}`
- **Difference — hiệu: A \ B**
  - Thuộc A nhưng không thuộc B
  - Ví dụ `{1, 2}`
  - `B \ A = {4}` → hiệu không có tính giao hoán
- **Symmetric Difference — hiệu đối xứng: A △ B**
  - Thuộc đúng một trong hai tập
  - `(A \ B) ∪ (B \ A)`
  - Cũng bằng `(A ∪ B) \ (A ∩ B)`
  - Ví dụ `{1, 2, 4}`
- **Biểu thức nhiều bước**
  - Làm theo dấu ngoặc; viết rõ tập trung gian
  - Ví dụ A = `{1, 2, 3, 4}`, B = `{3, 4, 5}`, C = `{2, 5}`
    - `A ∪ B = {1, 2, 3, 4, 5}`
    - `(A ∪ B) \ C = {1, 3, 4}`
    - Cardinality = 3

### Cardinality — Số phần tử
- Với tập hữu hạn: liệt kê phần tử phân biệt rồi đếm
- `|∅| = 0`
- `|A ∪ B| = |A| + |B| − |A ∩ B|`
- `|A \ B| = |A| − |A ∩ B|`
- `|A △ B| = |A| + |B| − 2|A ∩ B|`
- **Checklist**
  - Tính đúng tập kết quả trước
  - Bỏ phần tử trùng
  - Với nested sets, đếm phần tử ở cấp ngoài cùng
  - Đếm lại trước khi chọn đáp án
- Ví dụ `{1, 3, 5, 4, 7}` có 5 phần tử; thứ tự viết không ảnh hưởng cardinality

### Functions — Hàm số
- **Ký hiệu**: `f: A → B`
  - A: domain — miền xác định
  - B: codomain — tập đích
  - `f(A)`: range/image — tập giá trị thực sự nhận được
  - Luôn có `f(A) ⊆ B`
- **Điều kiện là hàm**
  - Mỗi phần tử domain có đúng một output trong codomain
  - Một input có hai output → không phải hàm
  - Có input không được gán output → không phải hàm trên toàn domain đó
  - Nhiều input cùng một output → vẫn có thể là hàm
  - Một phần tử codomain không được dùng → vẫn có thể là hàm
- **Ví dụ**
  - `A = {1, 2}`, `B = {a, b, c}`
  - `f(1) = a`, `f(2) = a`
  - Domain A; codomain B; range `{a}`
- Tính chất hàm phụ thuộc cả công thức, domain và codomain

### Function Composition — Hàm hợp
- `(g ∘ f)(x) = g(f(x))`
- Thực hiện f trước, g sau — đọc từ phải sang trái
- Cần output của f nằm trong domain của g
  - Điều kiện đủ thường gặp: `f: A → B`, `g: B → C`
- Ví dụ `f(x) = x + 1`, `g(x) = 2x`
  - `(g ∘ f)(x) = 2(x + 1) = 2x + 2`
  - `(f ∘ g)(x) = 2x + 1`
  - Nói chung `g ∘ f ≠ f ∘ g`

### Types of Functions — Các loại hàm
- **Injective — đơn ánh / one-to-one**
  - Hai input khác nhau không có cùng output
  - Tương đương: `f(x₁) = f(x₂) ⇒ x₁ = x₂`
  - Kiểm tra phản ví dụ: tìm hai input khác nhau có cùng output
- **Surjective — toàn ánh / onto**
  - Mỗi phần tử codomain có ít nhất một preimage trong domain
  - `Range = Codomain`
  - Để kiểm tra: với y bất kỳ ở codomain, có giải được `f(x) = y` với x thuộc domain không?
- **Bijective — song ánh**
  - Vừa injective vừa surjective
  - Mỗi phần tử codomain có đúng một preimage
- **Tập hữu hạn A, B**
  - Injective ⇒ `|A| ≤ |B|`
  - Surjective ⇒ `|A| ≥ |B|`
  - Bijective ⇒ `|A| = |B|`
  - Nếu `|A| = |B|` và f là hàm: injective ⇔ surjective ⇔ bijective
  - Kích thước phù hợp chỉ là điều kiện cần, không tự chứng minh một mapping cụ thể injective/surjective
- **Ví dụ phụ thuộc domain/codomain**
  - `f: ℝ → ℝ`, `f(x) = 2x + 1`: bijective
  - `f: ℤ → ℤ`, `f(x) = 2x`: injective, không surjective vì bỏ các số lẻ
  - `f: ℝ → ℝ`, `f(x) = x²`: không injective vì f(1) = f(−1); không surjective vì không nhận giá trị âm
  - `f: ℝ → [0, ∞)`, `f(x) = x²`: surjective nhưng không injective
  - `f: [0, ∞) → [0, ∞)`, `f(x) = x²`: bijective

### Cartesian Product — Tích Descartes
- **Ordered pair — cặp có thứ tự**: `(a, b)`
  - Nói chung `(a, b) ≠ (b, a)`
  - `(a, b) = (c, d)` khi a = c và b = d
- `A × B = {(a, b) | a ∈ A, b ∈ B}`
- Ví dụ `A = {1, 2}`, `B = {x, y}`
  - `A × B = {(1, x), (1, y), (2, x), (2, y)}`
  - Ghép mỗi phần tử A với mọi phần tử B
- **Cardinality**: `|A × B| = |A| · |B|` với các tập hữu hạn
- `A × ∅ = ∅`, `∅ × B = ∅`
- Nói chung `A × B ≠ B × A`
- **Có điều kiện**
  - Tạo các cặp hợp lệ, rồi giữ cặp thỏa điều kiện
  - A = B = `{1, 2}`, điều kiện a < b → chỉ còn `{(1, 2)}`
  - Không dùng ngay `|A| · |B|` cho tập cặp đã bị lọc nếu chưa xét điều kiện
- **Phân biệt**: Cartesian Product tạo các cặp, không nhân hai giá trị; công thức cardinality nhân số phần tử hai tập

### Power Set — Tập lũy thừa
- `P(A)` là tập chứa mọi tập con của A
- Các phần tử của `P(A)` đều là tập hợp
- Ví dụ `A = {1, 2}`
  - `P(A) = {∅, {1}, {2}, {1, 2}}`
  - Có cả ∅ và chính A
- **Cardinality**: `|P(A)| = 2^|A|` với A hữu hạn
  - Mỗi phần tử có hai lựa chọn: lấy hoặc không lấy vào tập con
  - `|A| = 3` → `|P(A)| = 8`
- **Nested power set**
  - `|P(P(A))| = 2^(2^|A|)`
  - `|A| = 2` → `|P(A)| = 4` → `|P(P(A))| = 16`
- **Kết hợp Cartesian Product**
  - `|P(A) × B| = 2^|A| · |B|`
  - `|P(A × B)| = 2^(|A|·|B|)`
  - Đọc kỹ dấu ngoặc: đây là hai tập khác nhau

### Element vs Subset — Phần tử và tập con
- `x ∈ A`: kiểm tra x có xuất hiện trực tiếp trong A không
- `X ⊆ A`: kiểm tra từng phần tử của tập X có thuộc A không
- **Liên hệ quan trọng**
  - `X ∈ P(A) ⇔ X ⊆ A`
  - `x ∈ A ⇔ {x} ⊆ A ⇔ {x} ∈ P(A)`
- Với `A = {1, 2}`
  - `1 ∈ A`: đúng
  - `{1} ⊆ A`: đúng
  - `{1} ∈ A`: sai
  - `{1} ∈ P(A)`: đúng
  - `1 ∈ P(A)`: sai
- **Empty set**
  - `∅ ⊆ A`: luôn đúng
  - `∅ ∈ P(A)`: luôn đúng
  - `∅ ∈ A`: chỉ đúng nếu A trực tiếp chứa phần tử ∅
  - `∅ ≠ {∅}`: cardinality lần lượt là 0 và 1
  - `P(∅) = {∅}`; `|P(∅)| = 1`
- **Nested sets**
  - `A = {1, {2}}`: có hai phần tử là 1 và `{2}`
  - `{2} ∈ A`: đúng; `2 ∈ A`: sai
  - `{{2}} ⊆ A`: đúng vì phần tử duy nhất của `{{2}}` là `{2}`
  - `{2} ⊆ A`: sai vì 2 không thuộc A
  - Đếm dấu ngoặc và giữ nguyên cấu trúc; không tự bỏ một lớp `{}`

### Cách giải bài cơ bản
- **Tập hợp nhiều bước**: làm từng ngoặc → liệt kê tập kết quả → bỏ trùng → đếm
- **Mapping có phải hàm không?**: mỗi input đúng một output
- **Injective?**: có hai input khác nhau chung output không?
- **Surjective?**: có phần tử codomain bị bỏ sót không?
- **Hàm hợp**: thực hiện hàm bên phải trước, kiểm tra domain
- **Cartesian Product**: tạo ordered pairs, giữ thứ tự hai vị trí
- **Power Set**: phân biệt số phần tử ban đầu và số tập con; dùng lũy thừa đúng cấp
- **∈ hay ⊆?**: xem vế phải chứa trực tiếp đối tượng gì; với ⊆, kiểm tra các phần tử của vế trái

## Tuần 2 · 02–08/11/2026

### Propositional Logic — Logic mệnh đề
- **Proposition** là phát biểu có truth value True hoặc False.
- **Negation** ¬p đảo giá trị chân lý. Double negation ¬¬p ≡ p.
- **Conjunction** p ∧ q đúng khi cả hai đúng.
- **Disjunction** p ∨ q đúng khi có ít nhất một vế đúng, kể cả khi cả hai đúng (inclusive OR).
- **Implication** p → q chỉ sai khi p đúng và q sai. p là hypothesis/antecedent, q là conclusion/consequent.
  - Khi p sai, p → q đúng (vacuous truth).
  - Converse là q → p. Hai chiều có thể khác giá trị chân lý.
- **Biconditional** p ↔ q đọc là “p if and only if q”. Đúng khi hai vế cùng truth value.
  - p ↔ q ≡ (p → q) ∧ (q → p).
- **Truth table** với k biến có 2^k cách gán. Tạo cột cho biểu thức con rồi tính từ trong ngoặc ra ngoài.

### Logical Equivalence — Tương đương logic
- P ≡ Q khi chúng có cùng truth value ở mọi cách gán. Có thể kiểm tra bằng hai cột cuối trong truth table.
- **Implication**: (p → q) ≡ (¬p ∨ q).
- **Negation of Implication**: ¬(p → q) ≡ p ∧ ¬q.
- **De Morgan**
  - ¬(p ∧ q) ≡ ¬p ∨ ¬q.
  - ¬(p ∨ q) ≡ ¬p ∧ ¬q.
- **Commutative**: p ∧ q ≡ q ∧ p và p ∨ q ≡ q ∨ p.
- **Distributive**
  - p ∧ (q ∨ r) ≡ (p ∧ q) ∨ (p ∧ r).
  - p ∨ (q ∧ r) ≡ (p ∨ q) ∧ (p ∨ r).
- **Absorption**
  - p ∨ (p ∧ q) ≡ p.
  - p ∧ (p ∨ q) ≡ p.
  - Ví dụ ¬¬p ∧ (p ∨ ¬q) ≡ p ∧ (p ∨ ¬q) ≡ p. Bước đầu dùng Double Negation, bước sau dùng Absorption.
- **Satisfiability**
  - Satisfiable: có ít nhất một dòng True.
  - Unsatisfiable / contradiction: mọi dòng False, ví dụ p ∧ ¬p.
  - Tautology: mọi dòng True, ví dụ p ∨ ¬p. Mọi tautology đều satisfiable.

### Predicate & Quantifiers — Vị từ và lượng từ
- **Predicate** P(x) là phát biểu phụ thuộc x. Domain quy định các giá trị x được xét.
- **Universal** ∀x ∈ D, P(x) nghĩa là P đúng với mọi x trong D. Một counterexample đủ để bác bỏ.
- **Existential** ∃x ∈ D, P(x) nghĩa là có ít nhất một x trong D làm P đúng. Chỉ cần tìm một witness.
- **Phủ định lượng từ**
  - ¬(∀x ∈ D, P(x)) ≡ ∃x ∈ D, ¬P(x).
  - ¬(∃x ∈ D, P(x)) ≡ ∀x ∈ D, ¬P(x).
  - Giữ domain, đổi lượng từ, rồi phủ định predicate. Ví dụ phủ định “Every x in D satisfies x > 3” là “Some x in D satisfies x ≤ 3”.
  - Nếu predicate có AND hoặc OR, áp dụng De Morgan khi đẩy phủ định vào trong.

### Binary Relations — Quan hệ hai ngôi
- Quan hệ R trên tập A là tập con của A × A. aRb nghĩa là (a,b) ∈ R.
- **Ordered pairs**: liệt kê trực tiếp các cặp thuộc R.
- **Relation matrix**: phần tử Mᵢⱼ = 1 nếu (aᵢ,aⱼ) ∈ R. Dùng cùng thứ tự phần tử cho hàng và cột.
- **Directed graph**: aRb tương ứng mũi tên a → b. Cặp (a,a) là self-loop.
- **Reflexive**: ∀a ∈ A, aRa. Đường chéo chính toàn 1. Thiếu một self-loop là phản ví dụ.
- **Symmetric**: aRb ⇒ bRa. Mỗi cặp có cặp đảo. Relation matrix đối xứng.
- **Antisymmetric**: aRb ∧ bRa ⇒ a = b. Hai phần tử khác nhau có quan hệ theo cả hai chiều là phản ví dụ.
  - Symmetric và Antisymmetric có thể cùng đúng. Quan hệ bằng nhau là một ví dụ.
- **Transitive**: aRb ∧ bRc ⇒ aRc.
  - Tìm hai cặp nối được tại b, rồi kiểm tra cặp tắt (a,c). Phản ví dụ là hai cặp đầu có mặt nhưng cặp tắt vắng mặt.
  - Nếu có aRb và bRa, tính bắc cầu yêu cầu cả aRa và bRb.

### Equivalence Relations — Quan hệ tương đương
- Cần đủ Reflexive + Symmetric + Transitive.
- **Equivalence class** [a] = {x ∈ A | xRa}. Dấu | đọc là “sao cho”.
- Hai phần tử liên hệ với nhau thì có cùng lớp. Hai lớp khác nhau không giao nhau. Các lớp phủ hết A và tạo thành một partition.
- Ví dụ same parity trên ℤ là một quan hệ tương đương. Các lớp là số chẵn và số lẻ.

### Order Relations — Quan hệ thứ tự
- **Partial order** cần Reflexive + Antisymmetric + Transitive.
- **Comparable**: aRb hoặc bRa. Nếu cả hai chiều đều không có, a và b incomparable.
- **Total / Linear order**: partial order và mọi cặp phần tử đều comparable.
- Ví dụ ≤ trên ℤ là total order. Quan hệ chia hết trên số nguyên dương là partial order, với 2 và 3 incomparable. Quan hệ ⊆ trên P({1,2}) là partial order, với {1} và {2} incomparable.
