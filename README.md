# PHP-note
## Clean Code
### Biến:
- Đặt tên biến có ý nghĩa
- Dùng chung từ vựng để đặt tên cho các biến cùng loại
- Truyền vào biến có thể tìm lại được thay vì giá trị cụ thể
- Dùng biến để giải thích
- Tránh lồng quá sâu và trả về sớm
- Tránh map vô tội vạ
- Không thêm các nội dung không cần thiểt
- Dùng các tham số mặc định thay vì rút gọn
### So sánh
- Sử dụng so sánh xác định (cả type và value)
### Hàm 
- Không quá 2 tham số
- Mỗi hàm thực hiện một việc duy nhất
- Tên hàm thể hiện được chức năng của hàm
- Chỉ nên dừng lại ở một mức abstraction
- Không dùng flag như là tham số của hàm
- Tránh tác dụng phụ
- Không viết các hàm global
- Không sử dụng Singleton pattern
- Đóng gói điều kiện
- Tránh các điều kiện phủ định
- Tránh type-checking
- Loại bỏ code vô dụng
### Đối tượng và cấu trúc dữ liệu
- Sử dụng đóng gói đối tượng
- Tạo các thành phần private/protected cho đối tượng
### Class
- Ưu tiên tích hợp hơn là kế thừa
- Tránh các fluent interface
- Ưu tiên các class final

## Các nguyên lý SOLID
- **S**-RP : Single Responsibility Principle - Nguyên lý đơn nhiệm 
  - Một class chỉ nên giữ 1 trách nhiệm duy nhất (Chỉ có thể sửa đổi class với 1 lý do duy nhất)
- **O**-CP : Open Closed Principle - Nguyên lý mở của đóng
  - Có thể thoải mái mở rộng 1 class, nhưng không được sửa đổi bên trong class đó 
- **L**-SP : Liskov Subtitution Principle - Nguyên lý thay thế Liskov
  - Trong một chương trình, các object của class con có thể thay thế class cha mà không làm thay đổi tính đúng đắn của chương trình
- **I**-SP : Interface Segregation Principle - Nguyên lý phân chia interface
  - Thay vì dùng 1 interface lớn, ta nên tách thành nhiều interface nhỏ, với nhiều mục đích cụ thể
- **D**-IP : Dependency Inversion Principle - Nguyên lý phụ thuộc ngược
  - Các module cấp cao không nên phụ thuộc vào các modules cấp thấp. Cả 2 nên phụ thuộc vào abstraction.
  - Interface (abstraction) không nên phụ thuộc vào chi tiết, mà ngược lại.

## Các chuẩn PSR (PHP Standards Recommendations)
> PSR có nghĩa là PHP Standards Recommendations, nó là tiêu chuẩn được khuyến nghị áp dụng khi lập trình PHP và được các lập trình viên, tổ chức chấp nhận sử dụng.

> PSR được soạn thảo, đánh giá và khuyến khích sử dụng bởi một nhóm chuyên gia PHP những người phát triển cho các Framework và hệ thống PHP phổ biến (thành viên PSR).

### PSR-1 Basic Coding Standard (Tiêu chuẩn cơ bản khi viết code PHP)
- Các file code PHẢI sử dụng thẻ <?php hoặc <?
- File code PHP sử dụng encode: UTF-8 without BOOM
- Các Files NÊN hoặc dùng để khai báo các thành phần PHP (các lớp, hàm, hằng …) hoặc dùng với mục đích làm hiệu ứng phụ (như include, thiết lập ini cho PHP …), nhưng KHÔNG NÊN dùng cả 2 cùng lúc trong 1 file (Xem ví dụ này ở  Ví dụ 1)
- Các Namespace và classes PHẢI theo chuẩn “autoloading” PSR: [PSR-4]
- Tên lớp PHẢI có dạng NameClass (chữ không nameclass, Nameclass, namClass …)
- Hằng số trong class tất cả PHẢI viết HOA và chia ra bởi dấu _ (ví dụ ahdsoft_member).
- Tên phương thức của lớp PHẢI ở dạng camelCase (từ đầu viết thường, ví dụ: helloWorld).

### PSR-2 Coding Style Guide (Tiêu chuẩn trình bày code)
- Code PHẢI tuân thủ PSR-1
- Code PHẢI sử dụng 4 ký tự space để lùi khối (không dùng tab)
- Mỗi dòng code PHẢI dưới 120 ký tự, NÊN dưới 80 ký tự.
- PHẢI có 1 dòng trắng sau namespace, và PHẢI có một dòng trắng sau mỗi khối code.
- Ký tự mở lớp { PHẢI ở dòng tiếp theo, và đóng lớp } PHẢI ở dòng tiếp theo của thân class.
- Ký tự { cho hàm PHẢI ở dòng tiếp theo, và ký tự } kết thúc hàm PHẢI ở dòng tiếp theo của thân hàm.
- Các visibility (public, private, protected)  PHẢI được khai báo cho tất cả các hàm và các thuộc tính của lớp;
- Các từ khóa điều khiển khối(if, elseif, else) PHẢI có một khoảng trống sau chúng; hàm và lớp thì KHÔNG ĐƯỢC làm như vậy.
- Mở khối { cho cấu trúc điều khiển PHẢI trên cùng một dòng; và đóng khối này } với ở dòng tiếp theo của thân khối.
- Hằng số true, false, null PHẢI viết với chữ thường.
- Từ khóa extends và implements phải cùng dòng với class.
- implements nhiều lớp, thì mỗi lớp trên một dòng
- keyword var KHÔNG ĐƯỢC dùng sử dụng khai báo property.
- Tên property KHÔNG NÊN có tiền tố _ nhằm thể hiện thuộc protect hay private.
- Tham số cho hàm, phương thức: KHÔNG được thêm space vào trước dấu , và PHẢI có một space sau ,. Các tham số CÓ THỂ trên nhiều dòng, nếu làm như vậy thì PHẢI mỗi dòng 1 tham số.
- abstract, final PHẢI đứng trước visibility, còn static phải đi sau.

### PSR-3 Logger Interface (Giao diện logger)
- LoggerInterface với 8 phương thức ghi log theo chuẩn RFC 5424 thương sẽ được chia thành key log: debug, info, notice, warning, error, critical, alert, emergency.
- Mọi method chỉ chấp nhận một string tin nhắn, hoặc object dùng method a__toString() để chuyển tất cả sang tring.
- Message phải chứa placeholders với implementors phải replace giá trị từ array.
- Tên placeholders phải phù hợp với key log.
- Tên placeholders phải được phân cách bằng dấu ngoặc nhọn { và dấu ngoặc nhọn }.
- KHÔNG được chứa bất kỳ khoảng trắng giữa các ký tự tên placeholders.
chỉ NÊN gồm các ký tự A-Z, a-z, 0-9, dấu gạch dưới _, và thời gian,.. Việc sử dụng các ký tự khác thì để xem trong tương lai có được áp dụng không.Implementors CÓ THỂ sử dụng giữ chỗ để thực hiện các chiến lược thoát khác nhau và dịch các bản ghi để hiển thị. Người dùng KHÔNG NÊN pre-escape giá trị giữ chỗ vì họ không thể biết trong đó bối cảnh các dữ liệu sẽ được hiển thị.

### PSR-4 Autoloading Standard (Tiêu chuẩn về tự động nạp)
- Tên xác định đầy đủ của một lớp có dạng:
> \<NamespaceName>(\<SubNamespaceNames>)*\<ClassName>

  - Tên xác định đầy đủ PHẢI có một namespace gốc (hiểu là tên vendor)
  - Tên xác định đầy đủ có thể có một hoặc nhiều namespace con.
  - Tên đầy đủ nó phải có một tên lớp kết thúc (ClassName)
- Khi một nạp một file thì nó phải tương ứng với một tên xác định đầy đủ của lớp.
  - Mỗi tên xác định đầy đủ phải tương ứng với một cấu trúc thư mục
  - Tên lớp kết thúc tương ứng với tên file:
  
### PSR-6 Caching Interface (Giao diện về Caching)
### PSR-7 HTTP Message Interface (Tiêu chuẩn Giao diện thông điệp HTTP)
> PSR-7 HTTP Message Interface là tiêu chuẩn về giao diện (thành phần cần có) của một ứng dụng sử dụng thông điệp HTTP (HTTP Message – request và respone), nó căn cứ vào các tiêu chuẩn RFC 7230, RFC 7231, RFC 3986.

## Design Patterns
Đến nay có 23 design pattern đã được biết đến, và chúng có thể được chia thành 3 nhóm dựa vào mục đích của chúng:
- Creational Patterns: được sử dụng để cấu trúc các đối tượng sao cho chúng có thể được tách ra khỏi hệ thống triển khai của chúng.
  - Abstract Factory
  - Builder
  - Factory Method
  - Prototype
  - Singleton
- Structural Patterns: được sử dụng để tạo thành các cấu trúc đối tượng lớn giữa nhiều đối tượng khác nhau.
  - Adapter
  - Bridge
  - Composite
  - Decorator
  - Facade
  - Flyweight
  - Proxy
- Behavioral Patterns: được sử dụng để quản lý các thuật toán, mối quan hệ và trách nhiệm giữa các đối tượng.
  - Chain of Responsibility
  - Command
  - Interpreter
  - Iterator
  - Mediator
  - Memento
  - Observer
  - State	
  - Strategy
  - Template Method
  - Visitor
