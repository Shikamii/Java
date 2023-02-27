# GIỚI THIỆU CHUNG

## I. Syntax cơ bản:

#### 1. Nhập xuất

##### a. Chương trình đầu tiên

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```
*`class`*: được sử dụng để khai báo một lớp trong Java

*`public`*: là một Access Modifier biểu diễn tính nhìn thấy, nhìn thấy tất cả

*`static`*: là từ khoá, mà nếu chúng ta khai báo bất cứ phương thức nào là static thì nó còn được gọi là **phương thức tĩnh** hoặc **phương thức static**. 

=> Đối với phương thức static là không cần thiết tạo đối tượng để triệu hồi phương thức static. Phương thức ` main ` được thực thi bởi JVM, vì thế bạn không cần thiết tạo một đối tượng để gọi phương thức main => tiết kiệm bộ nhớ.


**`void`**: là kiểu trả về của phương thức, nghĩa là phương thức không trả về bất cứ giá trị nào.

**`main`**: đại diện cho khởi động chương trình.

**`String[] args`**: được sử dụng cho tham số dòng lệnh.

**`System.out.println()`**: được sử dụng như là lệnh in. 

Có nhiều cách viết 1 chương trình java
```java
    static public void main(String args[])

    public static void main(String[] args)  
    public static void main(String []args)  
    public static void main(String args[])   

    public static void main(String... args)

    <void luôn đứng trước với main>
```
**Cấu trúc của một chương trình Java**
https://kungfutech.edu.vn/bai-viet/java/cau-truc-mot-chuong-trinh-java

##### b. Nhập xuất từ màn hình console trong Java

###### b.1 Nhập dữ liệu từ bàn phím

Để nhập dữ liệu từ bàn phím trong Java, chúng ta sử dụng lớp Scanner
>lớp Scanner là một lớp nằm trong gói java.util, được sử dụng để đọc dữ liệu đầu vào từ các nguồn khác nhau như luồng đầu vào, người dùng, tệp

Đầu tiên phải import thử viện vào: **`import java.util.Scanner`**;

Tạo đối tượng từ lớp `Scanner`: **`Scanner scan = new Scanner(System.in);`**

```java
import java.util.Scanner;
Scanner scan = new Scanner(System.in)

// Scanner: là lớp giúp chúng ta lấy dữ liệu đầu vào, nằm trong gói java.util

// scan: là đối tượng được tạo ra từ lớp Scanner, khi nhập, ta sẽ làm việc với đối tượng này

// () trong ngoặc này có thể là hệ thống, người dùng or têp.

// system.in: đây chính là lấy dữ liệu từ hệ thống(console)

public class NhapXuat {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Nhập tên của bạn: ");
        String name = scanner.nextLine();
        System.out.println("Tên của bạn là: " + name);
    }

}
Nhập tên của bạn: NAD
Tên của bạn là: NAD
```
**Cú pháp **

>`(data-type) (variable-name) = scan.next...();`

|Phương thức| Mô tả|
|---|---|
|nextByte()|	Đọc một số nguyên kiểu byte|
|nextShort()|	Đọc một số nguyên kiểu short|
|nextInt()	|Đọc một số nguyên kiểu int|
|nextLong()	|Đọc một số nguyên kiểu long|
|nextDouble()	|Đọc một số kiểu double|
|next()	|Đọc một string kết thức trước một ký tự trắng|
|nextLine()	|Đọc một line of text (kết thúc bằng phím Enter)|


###### b.2 Xuất dữ liệu ra màn hình

`System.out.println(“ ”);` : Xuất kết quả ra màn hình đồng thời con trỏ chuột nhảy xuống dòng tiếp theo.

```java
    Scanner scanner = new Scanner(System.in);
    System.out.print("Nhập tên của bạn: ");
    String name = scanner.nextLine();
    System.out.println("Tên của bạn là: " + name);
```
`System.out.print(“ ”);`  : Xuất kết quả ra màn hình nhưng con trỏ chuột không xuống dòng.

`System.out.printf(“ ”);`  : Xuất ra màn hình kết quả đồng thời có thể định dạng được kết quả đó nhờ vào các đối số thích hợp.

>**`Giống printf trong C`**
![Alt text](https://caodang.fpt.edu.vn/wp-content/uploads/3.jpg-1.png)


#### 2. Biến
Trong Java, **`Biến`** là một cái tên được gán cho một vùng nhớ lưu trữ giá trị trong chương trình 

**Có 3 kiểu biến trong Java**

- Biến cục bộ(biến local)
- Biến toàn cục(biến instance)
- Biến tĩnh(biến static)

**Có 2 kiểu dữ liệu trong Java**
- Kiểu dữ liệu nguyên thuỷ(primitive)
- Kiểu dữ liệu đối tượng(kiểu lớp bao: swapper class)

`Cú pháp khai báo biến`
```java
DataType varName [ = value] [, varName2] [ = value2]...;
```
DataType là kiểu dữ liệu của biến, varName là tên biến.


**Quy tắc đặt tên biến trong Java**
https://freetuts.net/cu-phap-va-quy-tac-java-co-ban-1028.html


```java
public class Bien {
    public static float PI = 3.14f;   // Đây là biến static
    int n;                            // Đây là biến instance
     
    public Bien () {
        char c = 'c';                 // Đây là biến local
    }
}
```
##### a. Biến local trong Java

- **Biến cục bộ được khai báo trong các `phương thức`, `hàm contructor` hoặc `trong các block`.**

- Biến cục bộ được tạo bên trong các phương thức, contructor, block và sẽ bị phá hủy khi kết thúc các phương thức, contructor và block.

- Không được sử dụng “`access modifier`” khi khai báo biến cục bộ.

- **Phải khởi tạo giá trị cho biến cục bộ trước khi có thể sử dụng.**

ví dụ: `khởi tạo biến local`:
```java
public class Bien {
     
    public void sayHello() {
        int n = 10;                     // Đây là biến local
        System.out.println("Gia tri cua n la: " + n);
    }
     
    public static void main(String[] args) {
        Bien bienLocal = new Bien();
        bienLocal.sayHello();
    }
}
Viết phương thức sayHello
ở phương thức main: tạo một object bienLocal của class Bien
object bienLocal gọi đến phương thức sayHello

Kết quả: Gia tri cua n la: 10
```

`Chú ý` : *nếu không khởi tạo giá trị cho biến local thì chương trình Java sẽ báo lỗi khi biên dịch*

##### b. Biến instance(biến toàn cục) trong Java

- Biến instance được khai báo trong một lớp(class), bên ngoài các phương thức, constructor và các block.

- Biến instance được lưu trong bộ nhớ heap. <còn biến local thì lưu trên bộ nhớ stack>

- Biến instance được tạo khi một đối tượng được tạo bằng việc sử dụng từ khóa “new” và sẽ bị phá hủy khi đối tượng bị phá hủy.

- Biến instance có thể được sử dụng bởi các phương thức, constructor, block, ... Nhưng nó phải được sử dụng thông qua một đối tượng cụ thể.

- **Được phép sử dụng "access modifier" khi khai báo biến toàn cục, mặc định là "default".**

- Biến instance có giá trị mặc định phụ thuộc vào kiểu dữ liệu của nó. Ví dụ nếu là kiểu int, short, byte thì giá trị mặc định là 0, kiểu double thì là 0.0d, ... Vì vậy, bạn sẽ không cần khởi tạo giá trị cho biến instance trước khi sử dụng.

- Bên trong class mà bạn khai báo biến instance, bạn có thể gọi nó trực tiếp bằng tên khi sử dụng ở khắp nới bên trong class đó.

Ví dụ về biến instance trong Java:
```java
public class Sinhvien {
    // biến instance "ten" kiểu String, có giá trị mặc định là null
    public String ten;
 
    // biến instance "tuoi" kiểu Integer, có giá trị mặc định là 0
    private int tuoi;
 
    // sử dụng biến ten trong một constructor
    public Sinhvien(String ten) {
        this.ten = ten;
    }
 
    // sử dụng biến tuoi trong phương thức setTuoi
    public void setTuoi(int tuoi) {
        this.tuoi = tuoi;
    }
 
    public void showStudent() {
        System.out.println("Ten  : " + ten);
        System.out.println("Tuoi : " + tuoi);
    }
 
    public static void main(String args[]) {
        Sinhvien sv = new Sinhvien("Nguyen Van A");
        sv.setTuoi(21);
        sv.showStudent();
    }
}

Kết quả
Ten  : Nguyen Van A
Tuoi : 21


```

##### c. Biến static trong Java
- Biến static được khai báo trong một class với từ khóa "static", phía bên ngoài các phương thức, constructor và block.

- Sẽ chỉ có duy nhất một bản sao của các biến static được tạo ra, dù bạn tạo bao nhiêu đối tượng từ lớp tương ứng. 

- Biến static được lưu trữ trong bộ nhớ static riêng.
Biến static được tạo khi chương trình bắt đầu chạy và chỉ bị phá hủy khi chương trình dừng.

- Giá trị mặc định của biến static phụ thuộc vào kiểu dữ liệu bạn khai báo tương tự biến instance.

- **Biến static được truy cập thông qua tên của class chứa nó, với cú pháp: TenClass.tenBien.**

- *Trong class, các phương thức sử dụng biến static bằng cách gọi tên của nó* `khi phương thức đó cũng được khai báo với từ khóa "static"`.

Ví dụ về biến static trong Java
```java
public class Sinhvien {
    // biến static 'ten'
    public static String ten = "Nguyen Van A";
     
    // biến static 'tuoi'
    public static int tuoi = 21;
 
    public static void main(String args[]) {
        // Sử dụng biến static bằng cách gọi trực tiếp
        System.out.println("Ten : " + ten);
 
        // Sử dụng biến static bằng cách gọi thông qua tên class
        System.out.println("Ten : " + Sinhvien.tuoi);
    }
}

kết quả:
Ten : Nguyen Van A
Ten : 21

```
##### d. các kiểu dữ liệu trong Java
Có hai hiểu dữ liệu trong Java

- Kiểu dữ liệu nguyên thuỷ

    ![](https://scontent.fhan2-4.fna.fbcdn.net/v/t1.15752-9/329967746_494048472918913_694210227649147808_n.png?_nc_cat=110&ccb=1-7&_nc_sid=ae9488&_nc_ohc=Ue6kcQD95xUAX89LZfM&_nc_ht=scontent.fhan2-4.fna&oh=03_AdRv5hD_eLmFtcpsx0HJt-wDRYKI51KaCimErMTVFUVNBA&oe=640B01B6)
- Kiểu dữ liệu đối tượng

    | Kiểu dữ liệu | Mô tả |
    | --- |---|
    |array|Một mảng của các dữ liệu cùng kiểu.|
    |class|Dữ liệu kiểu lớp đối tượng do người dùng định nghĩa. Chứa tập các thuộc tính và phương thức..|
    |interface| Dữ liệu kiểu lớp giao tiếp do người dùng định nghĩa. Chứa các phương thức của giao tiếp| 

#### 3. Toán tử

- toán tử số học: +, -, *, %, /, ++, --, +=...

- Toán tử bit: ~(not), &(and), |(or), ^, >>, <<, ...

- Toán tử quan hệ: ==, !=, >, >=, <, <=

- Toán tử logic: &&, ||, ^, !


#### 4.  If-else

- Mềnh đề if

    -> kiểm tra giá trị dạng boolean của điều kiện
    ```java
    if (condition) {  
    // khối lệnh này thực thi 
    // nếu condition = true
    } 
    ```
    ```java
    public class Test {
        public static void main(String[] args) {
            int age = 20;
            if (age > 18) {
                System.out.print("Tuổi lớn hơn 18");
            }
        }
    }
    kết quả: Tuổi lớn hơn 18
    ```
- Mệnh đề if else

    ```java
    if (condition) {
        // khối lệnh này được thực thi
        // nếu condition = true
    } else {
        // khối lệnh này được thực thi
        // nếu condition = false
    }
    ```
    ```java
    public class Test {
        public static void main(String[] args) {
            int number = 13;
            if (number % 2 == 0) {
                System.out.println("Số " + number + " là số chẵn.");
            } else {
                System.out.println("Số " + number + " là số lẻ.");
            }
        }
    }
    Kết quả: Số 13 là số lẻ.
    ```
- Mệnh đề if-else-if
```java
    if (condition1) {  
        // khối lệnh này được thực thi 
        // nếu condition1 là true  
    } else if (condition2) {  
        // khối lệnh này được thực thi 
        // nếu condition2 là true  
    }  else if (condition3) {  
        // khối lệnh này được thực thi 
        // nếu condition3 là true  
    }  
    ...  
    else {  
        // khối lệnh này được thực thi 
        // nếu tất cả những điều kiện trên là false                 
    }
```

#### 5. Vòng lặp
-> sử dụng để lặp đi lặp lại một phần của chương trình nhiều lần

- Vòng lặp for
```java
    for(int i=0; i<n; i++){

    }

    for(int i : a);
```
>NOTE: chúng ta có thể đặt tên cho mỗi vòng lặp for bằng cách đặt gán nhãn trước vòng lặp for

>-> tiện cho break

```java
public class LabeledForExample {
    public static void main(String[] args) {
        aa: for (int i = 1; i <= 3; i++) {
            bb: for (int j = 1; j <= 3; j++) {
                if (i == 2 && j == 2) {
                    break aa;
                }
                System.out.println(i + " " + j);
            }
        }
    }
}
```

- Vòng lặp While
```java
while(condition) {  
    // Khối lệnh được lặp lại cho đến khi condition = False
}  

public class WhileExample1 {
    public static void main(String[] args) {
        int i = 1;
        while (i <= 10) {
        System.out.println(i);
            i++;
        }
    }
}

while(true){
    // các câu lệnh
}
```

#### 6. Arrays
```java
khai báo mảng: <Kiểu dữ liệu>[] <tên mảng>;

Khởi tạo mảng: <Kiểu dữ liệu>[] <tên mảng> = new <kiểu dữ liệu>[số lượng phần tử];
<Kiểu dữ liệu>[] <tên mảng> = {value 0, value 1, ... value n};

-> ví dụ: int[] arr = new int[100];


Sắp xếp mảng:
import java.util.Arrays;

int[] arr = {4, 3, 2, 8 , 6};
Arrays.sort(arr);

```

`>sử dụng thuộc tính length để lấy số lượng phần tử của mảng`
Tìm hiểu thêm:
https://kungfutech.edu.vn/bai-viet/java/mang-array-trong-java


![](https://scontent.fhan2-4.fna.fbcdn.net/v/t1.15752-9/333730603_1411117176092523_4334721918916623627_n.png?_nc_cat=100&ccb=1-7&_nc_sid=ae9488&_nc_ohc=KhcaOccWsBkAX_G1D1g&_nc_ht=scontent.fhan2-4.fna&oh=03_AdTqgjjqNexqx5-gCPH9a5JXQBjIbiDjfQbIWJ1coVpIKA&oe=64248123)

#### Hàm trong java
cú pháp
```
modifier returnType nameOfMethod (Parameter List) {
   // method body
}
Modifiers: Tạm dịch là phạm vi sửa đổi và truy cập
returnType: Là kiểu dữ liệu trả về
nameOfMethod: Là tên của hàm (method)
Parameter là các tham số đầu vào của hàm (có thể có nhiều tham số với nhiều kiểu dữ liệu khác nhau)
method body: là các mã code bên trong hàm
```

ví dụ
```java
public class Test {

    public static int tongHaiSo(int a, int b) {
        return a + b;   // hàm trả về kết quả
    }

    public static void main(String[] args) {
        int sum = tongHaiSo(2,5);
        System.out.println(sum);
    }

    public static void printHello() {
        System.out.println("Hello");  // hàm không trả về kết quả
    }
}

```
Tìm hiểu thêm: https://kungfutech.edu.vn/bai-viet/java/ham-phuong-thuc-trong-java

#### String
https://viettuts.vn/java-string

https://kungfutech.edu.vn/bai-viet/java/string-trong-java

#### 7. Wapper class 

https://kungfutech.edu.vn/bai-viet/java/lop-wrapper-trong-java

Lớp Wrapper trong java cung cấp cơ chế để chuyển đổi kiểu dữ liệu nguyên thủy thành kiểu đối tượng và từ đối tượng thành kiểu dữ liệu nguyên thủy.

Sự chuyển đổi tự động kiểu dữ liệu nguyên thủy thành kiểu đối tượng được gọi là autoboxing và ngược lại được gọi là unboxing.

|Kiểu nguyên thủy|	Kiểu Wrapper|
|---|---|
|boolean	|Boolean|
|char	|Character|
|byte	|Byte|
|short	|Short|
|int	|Integer|
|long	|Long|
|float	|Float|
|double|	Double|

Ví dụ chuyển kiểu dữ liệu nguyên thủy thành kiểu Wrapper
```java
public class WrapperExample1 {
    public static void main(String args[]) {
        // Đổi int thành Integer (đổi sang lớp bao)
        int a = 20;
        Integer i = Integer.valueOf(a);// đổi int thành Integer
        Integer j = a;// autoboxing, tự động đổi int thành Integer trong nội bộ trình biên dịch
 
        System.out.println(a + " " + i + " " + j);
    }
}
```
Ví dụ chuyển kiểu Wrapper thành kiểu dữ liểu nguyên thủy

```java
public class WrapperExample2 {
    public static void main(String args[]) {
        // đổi Integer thành int
        Integer a = new Integer(3);
        int i = a.intValue();// đổi Integer thành int
        int j = a;// unboxing, tự động đổi Integer thành int trong nội bộ trình biên dịch
 
        System.out.println(a + " " + i + " " + j);
    }
}
```

**Từ một kiểu dữ liệu bình thường int, char,,, thì đều có thể chuyển nó sang dạng wrapper kiểu String**

![](https://scontent.fhan2-5.fna.fbcdn.net/v/t1.15752-9/330850834_918045222709847_6900395283448473138_n.png?_nc_cat=109&ccb=1-7&_nc_sid=ae9488&_nc_ohc=NldGOwUQa1wAX_3ZkjX&_nc_ht=scontent.fhan2-5.fna&oh=03_AdTan3jzIEsBClYYM73wL8ChN8KrWWDw28x4SmO_JwndcQ&oe=6411A8D3)


tìm hiểu thêm:
https://kungfutech.edu.vn/bai-viet/java/lop-wrapper-trong-java
#### 8. String classes
Việc xử lý các xâu ký tự trong Java được hỗ trợ bởi hai lớp String và StringBuffer

Lớp String dùng cho những xâu ký tự bất biến, nghĩa là những xâu chỉ đọc và sau khi dược khởi tạo giá trị thì nội dung bên trong xâu không thể thay đổi được. Lớp StringBuffer được sử dụng đối với những xâu ký tự động, tức là có thể thay đổi được nội dung bên trong của xâu.

tham khảo thêm: https://kungfutech.edu.vn/bai-viet/java/lop-string-trong-java
#### 9. Math class
- import java.lang.Math
- Khi cần gọi hàm nào thì chỉ cần Math. + hàm cần gọi

![](https://scontent.fhan2-3.fna.fbcdn.net/v/t1.15752-9/329723183_1550754502075598_7003334989458999152_n.png?_nc_cat=101&ccb=1-7&_nc_sid=ae9488&_nc_ohc=qjWlBjHgYEsAX_sRNCZ&_nc_oc=AQkyW6tWHt7WD4UhusEfiX8ueaZYoLvUymEXP0OrgH4cPvWCwSzfU1NDPN1JeDBgEEs&_nc_ht=scontent.fhan2-3.fna&oh=03_AdRbmbKgBHEXQkTzvjvSXRaPIPiQpqmTmIGw3rX8sSVwtg&oe=640B0676)



## II. Regex
Java Regex hoặc Regular Expression (biểu thức chính quy) là một API để định nghĩa một mẫu để tìm kiếm hoặc thao tác với chuỗi. Nó được sử dụng rộng rãi để xác định ràng buộc trên các chuỗi như xác thực mật khẩu, email, kiểu dữ liệu datetime, ...

>Gói java.util.regex
Java Regex API cung cấp 1 interface và 3 lớp trong gói java.util.regex.

- Lớp Matcher và Pattern trong java cung cấp cơ sở của biểu thức chính quy. Gói java.util.regex cung cấp các lớp và giao diện sau cho các biểu thức chính quy.

        1. Interface MatchResult
        2. Lớp Matcher
        3. Lớp Pattern
        4. Lớp PatternSyntaxException

- Lớp Matcher
Nó implements interface MatchResult, cung cấp bộ máy xử lý biểu thức chính quy để thao tác với chuỗi ký tự.

|No.	|Phương thức	|Mô tả|
|---|---|---|
|1|	boolean matches()|	kiểm tra xem biểu thức chính quy có khớp với mẫu hay không.|
|2|	boolean find()|	tìm biểu thức tiếp theo khớp với mẫu.|
|3	|boolean find(int start)|	tìm biểu thức tiếp theo khớp với mẫu từ số bắt đầu đã cho.|
|4|	String group()	|trả về chuỗi con phù hợp.|
|5	|int start()	|trả về vị trí bắt đầu của chuỗi con phù hợp.|
|6|	int end()|	trả về vị trí kết thúc của chuỗi con phù hợp.|
|7|	int groupCount()|	trả về tổng số các chuỗi con phù hợp.|

- Lớp Pattern
Đây là phiên bản được biên dịch của một biểu thức chính quy. Nó được sử dụng để xác định một mẫu cho bộ máy regex.

|No.|	Phương thức|	Mô tả|
|---|---|---|
|1	|static Pattern compile(String regex)|	biên dịch regex đã cho và trả về thể hiện của Pattern.
|2	|Matcher matcher(CharSequence input)|	tạo một matcher khớp với đầu vào đã cho với mẫu.
|3	|static boolean matches(String regex, CharSequence input)	|Nó biên dịch biểu thức chính quy và tìm kiếm các chuỗi con từ chuỗi input phù hợp với mẫu regex.
4|	String[] split(CharSequence input)	|chia chuỗi input đã cho thành mảng các kết quả trùng khớp với mẫu đã cho.
|5	|String pattern()	|trả về mẫu regex.


- Cú pháp Regex trong Java
Các lớp ký tự Regex


|Regex	|Mô tả|
|---|---|
|[...]	|trả về một ký tự phù hợp|
|[abc]	|a, b, hoặc c|
|[^abc]	|Bất kỳ ký tự nào ngoại trừ a, b, hoặc c|
|[a-zA-Z]|	a tới z hoặc A tới Z|
|[a-d[m-p]]	|a tới d, hoặc m tới p: [a-dm-p]|
|[a-z&&[def]]	|d, e, hoặc f|
|[a-z&&[^bc]]	|a tới z, ngoại trừ b và c:[ad-z]|
[a-z&&[^m-p]]	|a tới z, ngoại trừ m tới p: [a-lq-z]|
|[0-9]	|0 tới 9|

- Số lượng ký tự trong Regex

Số lượng trong Regex chỉ định số lượng xảy ra của một ký tự.

|Regex|	Mô tả|	Pattern|	Ví dụ|
|---|---|---|---|
X?|	X xảy ra một hoặc không lần	|hellos?	|hello, hellos, helloss|
X+|	X xảy ra một hoặc nhiều lần|	Version \w-\w+	|Version A-b1_1|
X*|	X xảy ra không hoặc nhiều lần|	A*B*C*	|AAACC|
X{n}|	X chỉ xảy ra n lần|	\d{4}|	2018, 20189, 201|
X{n,}|	X xảy ra n hoặc nhiều lần|	\d{4,}	|2018, 20189, 201|
X{y,z}|	X xảy ra ít nhất y lần nhưng nhỏ hơn z lần|	\d{2,3}	|2018, 201|


- Ký tự đặc biệt trong Regex

|Regex|	Mô tả|
|---|---|
|.	|Bất kỳ ký tự nào|
|^	|Có 2 cách sử dụng.1. Đánh dấu bắt đầu của một dòng, một chuỗi.2. Nếuu sử dụng trong dấu [...] thì nó có nghĩa là phủ định.|
|$	|Đánh dấu Kết thúc của một dòng|
|\d|	Bất kỳ chữ số nào, viết tắt của [0-9]|
|\D	|Bất kỳ ký tự nào không phải chữ số, viết tắt của [^0-9]|
|\s|	Bất kỳ ký tự trống nào (như dấu cách, tab, xuống dòng, ...), viết tắt của [\t\n\x0B\f\r]|
|\S	|Bất kỳ ký tự trống nào không phải ký tự trống, viết tắt của [^\s]|
|\w	|Bất kỳ ký tự chữ nào (chữ cái và chữ số), viết tắt của [a-zA-Z_0-9]|
|\W	|Bất kỳ ký tự nào không phải chữ cái và chữ số, viết tắt của [^\w]|
\b	|Ranh giới của một từ|
\B	|Không phải ranh giới của một từ|


- Ký tự logic trong Regex

|Regex|	Mô tả|	Pattern	|Ví dụ|
|---|---|---|---|
||	|Hoặc|	22|33|	33|
|( … )	|Group các ký tự và chụp lại	|A(nt|pple)	Ant, Apple|
|\1|	Nội dung của Group 1|	r(\w)g\1x|	regex|
|\2	|Nội dung của Group 2|	(\d\d)\+(\d\d)=\2\+\1|	12+65=65+12|
|(?: … )	|Group không được chụp lại, bạn không thể sử dụng \1|	A(?:nt|pple)|	Ant, Apple|
## III. Class & Object:

#### 1. Encapsuluton <tính đóng gói>

Tính đóng gói trong Java là kỹ thuật ẩn giấu thông tin không liên quan và hiển thị thông tin liên quan

-> bảo vệ trạng thái bên trong của một đối tượng. việc sửa đổi phải thông qua các phương thức

Ví dụ
![](https://user-images.githubusercontent.com/29374426/130181521-4a08856a-756f-46f4-94f4-6ff1a0a90f18.png)

Public: công khai xi nhan, đèn bánh xe...
Private: đồ đạc trong cốp xe

```java
public class Person {
    // khai báo các thuộc tính của đối tượng là private
    private String cmnd;
    private String hoTen;

    // tạo các phương thức getter/setter
    // 2 phương thức getCmnd() và getHoTen() là phương thức getter
    // dùng để trả về số chứng minh nhân dân và họ tên của đối tượng
    // và kiểu trả về của hai phương thức này tương ứng với kiểu dữ liệu của thuộc tính
    // 2 phương thức setCmnd() và setHoTen() là phương thức setter
    // dùng để gán giá trị cho thuộc tính chứng minh nhân dân và họ tên của đối tượng
    // trong đó tham số truyền vào của 2 phương thức này được gọi là tham số (biến cục bộ)
    // và có kiểu dữ liệu tương ứng với kiểu dữ liệu của thuộc tính (biến đối tượng)
    public String getCmnd() {
        return cmnd;
    }

    // this là từ khóa có ý nghĩa là một tham chiếu đặc biệt
    // chiếu tới đối tượng chủ của phương thức hiện hành
    // this có thể được dùng để truy cập biến đối tượng (instance variable)
    // hoặc gọi phương thức đối với đối tượng hiện hành.
    // Thông thường, công dụng này của this chỉ có ích
    // khi tên biến đối tượng bị trùng với tham số (biến cục bộ - local variable) của phương thức
    public void setCmnd(String cmnd) {
        this.cmnd = cmnd;
    }
    public String getHoTen() {
        return hoTen;
    }
    public void setHoTen(String hoTen) {
        this.hoTen = hoTen;
    }

}

package vidu;

public class TestPerson {

    public static void main(String[] args) {
        Person person = new Person();

        // gán giá trị họ tên cho đối tượng person vừa tạo thông qua setHoTen()
        // và gán số chứng minh nhân dân thông qua setCmnd()
        person.setHoTen("NAD");
        person.setCmnd("12345678");

        // truy cập đến tên của đối tượng person thông qua phương thức getHoten()
        // và số chứng minh nhân dân thông qua phương thức getCmnd()
        System.out.println("Tên: " + person.getHoTen() + ", CMND: " + person.getCmnd());
    }

}
Tên: NAD, CMND: 12345678
```
#### 2. Inheritance <tính kế thừa>
Tính kế thừa cho phép xây dựng một lớp mới dựa trên các định nghĩa của lớp đã có. Có nghĩa là lớp cha có thể chia sẽ dữ liệu và phương thức cho các lớp con. Các lớp con khỏi phải định nghĩa lại, ngoài ra có thể mở rộng các thành phần kế thừa và bổ sung thêm các thành phần mới. Tái sử dụng mã nguồn 1 cách tối ưu, tận dụng được mã nguồn.

Tuy nhiên, lớp con chỉ được truy cập các thành viên public và protected của class cha. Nó không được phép truy cập đến thành viên private của class cha.

![](https://user-images.githubusercontent.com/29374426/131276922-2608f214-0690-4eb4-96e3-b7384d4b2df3.png)

ta sử dụng từ khoá `extends` để kế thừa

```java
class Subclass-name extends Superclass-name {  
   //methods and fields
}  
```
Ví dụ về kế thừa
```java
class Employee {
    float salary = 1000;
}
 
class Programmer extends Employee {
    int bonus = 150;
}
 
public class InheritanceSample1 {
    public static void main(String args[]) {
        Programmer p = new Programmer();
        System.out.println("Programmer salary is: " + p.salary);
        System.out.println("Bonus of Programmer is: " + p.bonus);
    }
}
Kết quả:
Programmer salary is: 1000.0
Bonus of Programmer is: 150
```

Ví dụ về đơn kế thừa, đa kế thừa, kế thừa thứ cấp xem ở

https://viettuts.vn/java/tinh-ke-thua-trong-java

#### 3. Polymorphism
Đa hình là khái niệm mà hai hoặc nhiều lớp có những phương thức giống nhau nhưng có thể thực thi theo những cách thức khác nhau

ví dụ: đa hình khác trong thực tế đó là ta có 2 con vật: chó, mèo. Cả 2 con vật này đều là lớp động vật. Nhưng khi ta bảo cả 2 động vật kêu thì con chó sẽ kêu gâu gâu, con mèo sẽ kêu meo meo.

Đa hình được chia thành hai loại
![](https://user-images.githubusercontent.com/29374426/131280717-ae65a2c9-0e6d-4b34-9b60-e0ebdd61331b.png)

- Đa hình trong thời gian chạy(runtime) 
là quá trình gọi phương thức đã đưỢc ghi đè trong thời gian thực thi chương trình

**Upcasting: Khi biến tham chiếu của lớp cha tham chiếu tới đối tượng của lớp con**

```java
class Bike {
    void run() {
        System.out.println("running");
    }
}
 
public class Splender extends Bike {
    void run() {
        System.out.println("running safely with 60km");
    }
 
    public static void main(String args[]) {
        Bike b = new Splender();// upcasting
        // biến tham chiều của lớp cha: new Splender()

        // Bike b: đối tượng của lớP con
        b.run();
    }
}
kết quả: running safely with 60km

```

xem thêm ví dụ ở: https://kungfutech.edu.vn/bai-viet/java/tinh-da-hinh-trong-oop

Tuy nhiên khi chúng ta truy cập thuộc tính của lớp con thì sẽ không bị ghi đè, mà nó sẽ truy cập thuộc tính của lớp cha.

```java
    class Bike{
        int speedlimit = 90;
    }

    class Honda3 extends Bike {
        int speedlimit = 150;
    }

    public static void main(String args[]){
        Bike obj=new Honda3();
        System.out.println(obj.speedlimit);//90
    }
kết quả: 90

đối tượng của lớp cha nhưng lại tham chiếu từ lớp con thì ko bị ghi đè nhaa
```

#### 4. Common Modifiers
Có hai loại cấp độ truy cập(Access Modifier) trong Java

- Access modifier: xác định phạm vi có thể truy cập của các biến , phương thức, constructor hoặc lớp để có thể hạn chế sự truy cập đến các thành viên của lớp, từ một đối tượng khác

        Private
        default
        protected
        public

- Non-access Modifier như static, abstract, synchronized, native, volatile, transient,...
![](https://user-images.githubusercontent.com/29374426/131236803-4e0e053a-1843-4d16-9306-46140849c6b4.png)

|Từ khoá|	Truy cập trong chính lớp đó|	Truy cập trong lớp con cùng gói|	Truy cập trong lớp con khác gói	|Truy cập trong lớp khác cùng gói	|Truy cập trong lớp khác khác gói|
|---|---|---|---|---|---|
|private|	X	|-|	-|	-|	-|
|protected	|X	|X	|X	|X	|-|
|public	|X|	X|	X	|X|	X|
|default	|X	|X	|-|	X	|-|

Trong bảng trên thì X thể hiện cho sự truy cập hợp lệ còn – thể hiện không thể truy cập vào thành phần này.

Chốt lại là:
|Access Modifier|	Function|
|---|---|
|Private|	Chỉ access trong class.|
|Default|	Chỉ trong package.|
|Protected|	Chỉ trong package and ngoài package thông qua child class.|
|Public	| Cái nào cũng được.|

>lưu ý
- Constructor cần để public để có thể thực hiện tính Kế thừa. (nếu constructor mà để private thì ko thể nào tạo instance bên ngoài class của nó)
- Nếu không khai báo Access Modifier, thì nó mặc định là default.

- Default Access Modifier là chỉ được phép truy cập trong cùng package.
- Protected access modifier được truy cập bên trong package và bên ngoài package nhưng phải kế thừa.

- Protected access modifier có thể được áp dụng cho biến, phương thức, constructor. Nó không thể áp dụng cho lớp.

Xem ví dụ ở https://viettuts.vn/java/access-modifier-trong-java

![](https://scontent.fhan2-5.fna.fbcdn.net/v/t1.15752-9/329826934_728124735625219_1097483599118444478_n.png?_nc_cat=104&ccb=1-7&_nc_sid=ae9488&_nc_ohc=4Yj5GjTMMIcAX_UP_cd&_nc_ht=scontent.fhan2-5.fna&oh=03_AdSGsRHGcOjLX5O065cKEYqQLCWcVoy86d0vh88Zg4RD8g&oe=640B380A)


![](https://scontent.fhan2-5.fna.fbcdn.net/v/t1.15752-9/330105613_1126128271393549_4183457739891090957_n.png?_nc_cat=107&ccb=1-7&_nc_sid=ae9488&_nc_ohc=Fl1bgZD-tHcAX_96Y8y&_nc_ht=scontent.fhan2-5.fna&oh=03_AdSVIRN8NxqjTFECjvVxPrUBop83fNYMiDnpwGcuYMf6sg&oe=640B2DA7)


#### 5. Modifier static
Từ khóa static trong Java được sử dụng chính để quản lý bộ nhớ. Chúng ta có thể áp dụng từ khóa static với các biến, các phương thức, các khối, các lớp lồng nhau(nested class). Từ khóa static thuộc về lớp chứ không thuộc về instance(thể hiện) của lớp.

- Biến static: Khi bạn khai báo một biến là static, thì biến đó được gọi là biến tĩnh, hay biến static.
- Phương thức static: Khi bạn khai báo một phương thức là static, thì phương thức đó gọi là phương thức static.
- Khối static: Được sử dụng để khởi tạo thành viên dữ liệu static

##### a. Biến static
- Biến static có thể được sử dụng để tham chiếu thuộc tính chung của tất cả đối tượng (mà không là duy nhất cho mỗi đối tượng), ví dụ như tên công ty của nhân viên, tên trường học của các sinh viên, ...
- Biến static lấy bộ nhớ chỉ một lần trong Class Area tại thời gian tải lớp đó.

```java
public class Student8 {
    int rollno;
    String name;
    static String college = "Bưu Chính Viễn Thông";
 
    Student8(int r, String n) {
        rollno = r;
        name = n;
    }
 
    void display() {
        System.out.println(rollno + " - " + name + " - " + college);
    }
 
    public static void main(String args[]) {
        Student8 s1 = new Student8(111, "Thông");
        Student8 s2 = new Student8(222, "Minh");
 
        s1.display();
        s2.display();
    }
}
kết quả: 
111 - Thông - Bưu Chính Viễn Thông
222 - Minh - Bưu Chính Viễn Thông
```

>Ghi chú: Thuộc tính static trong Java được chia sẻ tới tất cả đối tượng.

xem thêm ví dụ ở:
https://viettuts.vn/java/tu-khoa-static-trong-java

##### b. Phương thức static trong Java

Nếu bạn áp dụng từ khóa static với bất cứ phương thức nào, thì phương thức đó được gọi là phương thức static.

- Một phương thức static thuộc lớp chứ không phải đối tượng của lớp.
- Một phương thức static gọi mà không cần tạo một instance của một lớp.
- Phương thức static có thể truy cập biến static và có thể thay đổi giá trị của nó.

```java
public class Student9 {
    int rollno;
    String name;
    static String college = "Bưu Chính Viễn Thông";
 
    static void change() {
        // Thay đổi thuộc tính static (thuộc tính chung của tất cả các đối tượng)
        college = "Đại Học Công Nghệ";
    }
 
    Student9(int r, String n) {
        rollno = r;
        name = n;
    }
 
    void display() {
        System.out.println(rollno + " - " + name + " - " + college);
    }
 
    public static void main(String args[]) {
        Student9.change();
 
        Student9 s1 = new Student9(111, "Thông");
        Student9 s2 = new Student9(222, "Minh");
        Student9 s3 = new Student9(333, "Anh");
 
        s1.display();
        s2.display();
        s3.display();
    }
}
```
- Phương thức static không thể sử dụng biến non-static hoặc gọi trực tiếp phương thức non-static.
- Từ khóa this và super không thể được sử dụng trong ngữ cảnh static.

```java
class A {
    int a = 40;// non static
 
    public static void main(String args[]) {
        System.out.println(a);
}
Kết quả:
Compile Time Error
```

##### c. Khối static
- Được sử dụng để khởi tạo thành viên dữ liệu static.
- Nó được thực thi trước phương thức main tại lúc tải lớp.

ví dụ về khối static
```java
public class A2 {
    static {
        System.out.println("Khối static: hello !");
    }
 
    public static void main(String args[]) {
        System.out.println("Main: hello !");
    }
}
Kết quả:
Khối static: hello !
Main: hello !
```

>lưu ý: ko cần main vẫn chạy được, ta sử dụng khối static

```java
public class A3 {
    static {
        System.out.println("static block is invoked");
        System.exit(0);
    }
}
```
#### 6. Interfaces

#### 7. Abstract Classes
>tính trừu tượng trong Java là một tiến trình ẩn các cài đặt chi tiết và chỉ hiển thị tính năng tới người dùng.

**Một phương thức được khai báo là abstract và không có trình triển khai thì đó là phương thức trừu tượng.**

*Nếu bạn muốn một lớp chứa một phương thức cụ thể nhưng bạn muốn triển khai thực sự phương thức đó để được quyết định bởi các lớp con, thì bạn có thể khai báo phương thức đó trong lớp cha ở dạng abstract.*

Từ khóa abstract được sử dụng để khai báo một phương thức dạng abstract. Một phương thức abstract không có thân phương thức.(không có trình triển khai)

```java
Khai bao phuong thuc voi tu khoa abstract va khong co than phuong thuc
abstract void printStatus();
```

ví dụ: 
```java
abstract class Bike{  
  abstract void run();  
}  
class Honda4 extends Bike{  
    void run() {
        System.out.println("running safely..");
    }
 
    public static void main(String args[]) {  
        Bike obj = new Honda4();  
        obj.run();  
    }  
}  
Kết quả:
running safely..
```
>Bike là lớp trừu tượng chỉ chứa một phương thức trừu tượng là run. Trình triển khai của nó được cung cấp bởi lớp Honda.

Lưu ý
- Nếu trong lớp có phương thức trừu tượng thì lớp đó phải được khai báo là trừu tượng
- Nếu một lớp kế thừa từ lớp trừu tượng thì: hoặc chúng phải ghi đè tất cả các phương thức ảo của lớp cha, hoặc lớp đó phải là lớp trừu tượng
- Không thể tạo ra đối tượng của lớp trừu tượng


![](https://scontent.fhan2-5.fna.fbcdn.net/v/t1.15752-9/332873650_6082115645160549_7698206015188706367_n.png?_nc_cat=107&ccb=1-7&_nc_sid=ae9488&_nc_ohc=PSxpBbKv4C0AX_aXdAC&tn=qf_Q2_EjAnC2Tavm&_nc_ht=scontent.fhan2-5.fna&oh=03_AdQrixTyY1YUtFBzhcIxJgFfyW8kq7DB9qoSvX3gqzHx6w&oe=6424927C)
