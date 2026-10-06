# Bài tập 3 - Tư duy thiết kế theo Domain (DDD)

## 1. DDD là gì?

Domain-Driven Design (DDD) là phương pháp thiết kế phần mềm tập trung vào **nghiệp vụ cốt lõi của doanh nghiệp (Domain)**.

DDD giúp đội ngũ phát triển phần mềm xây dựng hệ thống dựa trên cách doanh nghiệp thực sự hoạt động, thay vì chỉ tập trung vào công nghệ hoặc database.

Mục tiêu chính của DDD là tạo ra sự gắn kết giữa **nghiệp vụ và code**, giúp hệ thống dễ hiểu, dễ thay đổi và phản ánh đúng yêu cầu của doanh nghiệp.

---

## 2. Ưu điểm của DDD

### 2.1. Code phản ánh nghiệp vụ

DDD giúp các thành phần trong code thể hiện rõ các khái niệm nghiệp vụ.

Ví dụ, trong hệ thống thương mại điện tử có thể có:

```text
Order
Customer
Product
Payment
Shipment
```

Các khái niệm này gần với cách doanh nghiệp mô tả hệ thống, giúp developer dễ hiểu mục đích của từng thành phần.

---

### 2.2. Tạo ra Ubiquitous Language

Ubiquitous Language là ngôn ngữ chung được sử dụng thống nhất giữa developer, business analyst, product owner và domain expert.

Ví dụ, nếu doanh nghiệp gọi một đối tượng là `Order`, thì cả team nghiệp vụ và team kỹ thuật đều sử dụng thuật ngữ `Order` thay vì mỗi bên gọi một tên khác nhau.

Điều này giúp giảm hiểu nhầm trong quá trình phát triển.

---

### 2.3. Tập trung vào nghiệp vụ cốt lõi

DDD giúp team xác định phần nào của hệ thống thực sự tạo ra giá trị và lợi thế cạnh tranh cho doanh nghiệp.

Thay vì chỉ quan tâm đến database hoặc framework, team tập trung vào việc giải quyết các vấn đề nghiệp vụ quan trọng.

---

### 2.4. Giảm sự phức tạp của hệ thống

DDD giúp chia hệ thống lớn thành các phần có ranh giới và trách nhiệm rõ ràng.

Khi mỗi phần tập trung vào một domain cụ thể, việc phát triển và bảo trì hệ thống sẽ dễ dàng hơn.

---

### 2.5. Hỗ trợ phát triển hệ thống lâu dài

Khi nghiệp vụ thay đổi, kiến trúc được tổ chức theo domain giúp team dễ xác định phần code cần thay đổi.

Điều này giúp giảm ảnh hưởng của một thay đổi đến toàn bộ hệ thống.

---

## 3. Nhược điểm và khó khăn của DDD

### 3.1. Đường cong học tập cao

DDD có nhiều khái niệm cần hiểu như:

* Domain
* Sub-domain
* Bounded Context
* Entity
* Value Object
* Aggregate
* Domain Service
* Ubiquitous Language

Nếu team chưa có kinh nghiệm, việc áp dụng DDD có thể gây khó khăn.

---

### 3.2. Tốn thời gian phân tích nghiệp vụ

DDD yêu cầu developer phải hiểu sâu về nghiệp vụ và thường xuyên trao đổi với Domain Expert.

Team có thể phải tổ chức nhiều buổi thảo luận hoặc workshop để xác định:

* Business Rules.
* Domain Model.
* Bounded Context.
* Business Process.

Điều này làm tăng thời gian ở giai đoạn phân tích ban đầu.

---

### 3.3. Có thể trở nên quá phức tạp

Nếu áp dụng DDD cho một hệ thống đơn giản, team có thể tạo ra nhiều abstraction và cấu trúc không cần thiết.

Ví dụ, một CRUD application đơn giản có thể không cần đầy đủ các khái niệm phức tạp của DDD.

---

### 3.4. Yêu cầu sự phối hợp giữa nhiều bên

DDD không chỉ là công việc của developer.

Để xây dựng Domain Model chính xác, cần sự phối hợp giữa:

```text
Developer
    ↕
Business Analyst
    ↕
Domain Expert
    ↕
Product Owner
```

Nếu các bên không thống nhất về nghiệp vụ, việc xây dựng hệ thống sẽ gặp khó khăn.

---

## 4. Khi nào nên áp dụng DDD?

DDD phù hợp với các hệ thống:

* Có nghiệp vụ phức tạp.
* Có nhiều Business Rules.
* Thường xuyên thay đổi theo nghiệp vụ.
* Có domain tạo ra lợi thế cạnh tranh.
* Có team đủ kinh nghiệm để duy trì mô hình domain.

Ví dụ:

* E-commerce.
* Banking.
* Insurance.
* Logistics.
* Healthcare.
* Financial systems.

---

## 5. Khi nào không nên áp dụng DDD?

DDD có thể không cần thiết đối với:

* CRUD application đơn giản.
* Website nhỏ.
* Hệ thống nội bộ có nghiệp vụ đơn giản.
* Prototype cần xây dựng nhanh.
* Dự án có thời gian và nguồn lực rất hạn chế.

Trong những trường hợp này, một kiến trúc đơn giản có thể phù hợp hơn.

---

## 6. DDD giải quyết vấn đề "Big Ball of Mud" như thế nào?

Khi dự án phát triển trong thời gian dài mà không có ranh giới rõ ràng, code có thể trở thành một "Big Ball of Mud".

DDD giúp giải quyết vấn đề này bằng cách:

```text
Big Ball of Mud
       ↓
Phân tích Domain
       ↓
Xác định Sub-domain
       ↓
Xác định Bounded Context
       ↓
Xây dựng Domain Model
       ↓
Code phản ánh nghiệp vụ
```

Nhờ đó, hệ thống có cấu trúc rõ ràng hơn và các phần nghiệp vụ được tách biệt.

---

## 7. Kết luận

DDD không đơn thuần là một kỹ thuật lập trình mà là một cách tiếp cận giúp team hiểu và mô hình hóa nghiệp vụ của doanh nghiệp.

Ưu điểm lớn nhất của DDD là tạo sự gắn kết giữa **business và code**, đồng thời sử dụng **Ubiquitous Language** để các bên cùng hiểu hệ thống theo một cách thống nhất.

Tuy nhiên, DDD có đường cong học tập cao, tốn thời gian phân tích và không phù hợp với mọi dự án.

Vì vậy, DDD nên được áp dụng khi hệ thống có **nghiệp vụ phức tạp và domain mang lại giá trị quan trọng cho doanh nghiệp**, thay vì áp dụng chỉ vì đây là một phương pháp thiết kế phổ biến.
