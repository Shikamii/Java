# MÔ HÌNH MVC

### Mô hình MVC là gì?

là `mẫu kiến trúc phần mềm` hay `mô hình thiết kế` *để tạo lập giao diện người dùng trên máy tính*. MVC chia một ứng dụng thành ba phần tương tác được với nhau, mỗi thành phần có một nhiệm vụ riêng biệt và độc lập với các thành phần khác.

M: Model: Quản lý, xử lý dữ liệu
V: View: Hiển thị dữ liệu cho người dùng
C: controller: Điều khiển sự tương tác giữa Model và View

![](https://viettuts.vn/images/struts2/mvc-la-gi.png)

Chức năng: Giúp **tách biệt** giữa `cách thức mà dữ liệu được xử lý bên trong nội hàm` với `phần dữ liệu hiện thị với người dùng`

Here Controller sẽ được nhận tất cả các yêu cầu của người dùng => sau đó sẽ làm việc với Model để chuẩn bị dữ liệu cho phần thiết kế View => sau đó View sẽ sử dụng các dữ liệu được chuẩn bị bởi Controller để hiện thị cho người dùng.

### Các thành phần trong MVC

##### Model
- là bộ phần có nhiệm vụ quản lý dữ liệu của ứng dụng
- Chức năng biểu diễn, vận chuyển thông tin để trình diễn (view) và xử lý (control)

- Chứa tất cả các nghiệp vụ logic, đối tượng mô tả dữ liệu, ...

##### View
- Tương tác với người sử dụng.
- Show kết quả từ tầng Controller<cái mà yêu cầu>
- Thu nhận các hoạt động, request của người sử dụng và chuyển cho tầng Controller xử lý.
- Hiểu một cách đơn giản, View là hệ thống các frame, cửa sổ của ứng dụng; các trang giao diện web: html, jsp; Các bảng, mẫu biểu, báo cáo.

##### Controller

- Định nghĩa các hành vi, hoạt động, xử lý của hệ thống.
- Đối chiếu hành động của người sử dụng từ View. Đồng thời tương tác Model để gọi View và hiển thị thông tin tương ứng cho người dùng.

### Ưu nhược điểm của MVC

#### Ưu điểm
- Do được chia thành các phần độc lập => MÔ hình MVC giúp phát triển ứng dụng code dễ đọc, dễ nâng cấp, bảo trì.

- Thể hiện tính chuyên nghiệp trong việc tạo ứng dụng

#### Nhược điểm
- Đối với dự án nhỏ thì ko nên dùng MVC, sẽ cồng kềnh, tốn time trong quá trình phát triển và tốn time trung chuyển dữ liệu của các thành phần.

ví dụ Login sử dụng mô hình MVC

Tạo một project có cấu trúc như sau:

![](https://scontent.fhan3-5.fna.fbcdn.net/v/t1.15752-9/331076988_536523885245561_6632533815279756942_n.png?_nc_cat=109&ccb=1-7&_nc_sid=ae9488&_nc_ohc=Kq_Mbwcas7QAX-dy3Ha&_nc_ht=scontent.fhan3-5.fna&oh=03_AdSHz5Dj-Jgzf9E38M5u2CIIE0Tr8bCWQGs4drnaZK3iqA&oe=64167A01)

// lớp LoginModel.java

```java
package vn.viettuts.mvc;
 
public class LoginModel {
    private String userName;
    private String password;
 
    public LoginModel() {
    }
 
    public LoginModel(String userName, String password) {
        super();
        this.userName = userName;
        this.password = password;
    }
 
    public String getUserName() {
        return userName;
    }
 
    public void setUserName(String userName) {
        this.userName = userName;
    }
 
    public String getPassword() {
        return password;
    }
 
    public void setPassword(String password) {
        this.password = password;
    }
}
```

// Tạo view: LoginView.java
=> nhiệm vụ là hiện thị thông tin cho người dùng nhập vào

```java
package vn.viettuts.mvc;
 
import java.util.Scanner;
 
public class LoginView {
    public static Scanner scanner = new Scanner(System.in);
 
    public void showMessage(String smg) {
        System.out.println(smg);
    }
 
    public LoginModel getUserInfo() {  // kiểu trả về là một đối tượng của class gọi đến
        LoginModel user = new LoginModel();
        System.out.print("Username: ");
        user.setUserName(scanner.next());
        System.out.print("Password: ");
        user.setPassword(scanner.next());
        return user;
    }
}
```

// Tạo conTroller: LoginController.java

```java
package vn.viettuts.mvc;
 
public class LoginController {
    private LoginView view;
 
    public LoginController(LoginView view) {
        this.view = view;
    }
 
    public void login() {
        while (true) {
            LoginModel user = view.getUserInfo();
            if (checkLogin(user)) {
                view.showMessage("success!");
                break;
            } else {
                view.showMessage("wrong username or password!");
            }
        }
    }
 
    private boolean checkLogin(LoginModel user) {
        if ((user.getUserName().equals("admin")) 
                && (user.getPassword().equals("admin"))) {
            return true;
        }
        return false;
    }
 
    public LoginView getView() {
        return view;
    }
 
    public void setView(LoginView view) {
        this.view = view;
    }
}

```

Tạo lớp App.java chứa main để chạy ứng dụng

```java
package vn.viettuts.mvc;
 
public class App {
    public static void main(String[] args) {
        LoginView view = new LoginView();
        LoginController control = new LoginController(view);
        // goi ham login
        control.login();
    }
}
```
![](https://scontent.fhan3-4.fna.fbcdn.net/v/t1.15752-9/330853307_2242639972791900_7447531136912116682_n.png?_nc_cat=106&ccb=1-7&_nc_sid=ae9488&_nc_ohc=mzrZJPMnjLEAX-6zaMy&_nc_ht=scontent.fhan3-4.fna&oh=03_AdS5uttvY1DqUzKBWaMwJq4xT1GYY6cLZiAg6r1inLRHRw&oe=64168ADD)


# CÁC CÁCH ĐỌC GHI fILE


### Đọc ghi file sử dụng Byte Stream

- Có rất nhiều class Byte Stream, để hình dung Byte Stream hoạt động như thế nào, chúng ta sẽ tập trung vào FileInputStream và FileOutputStream

```java
public class CopyFileByte {
    public static void main(String [] args) throws IOException {
      FileInputStream inputStream = null;
      FileOutputStream outputStream = null;
 
      try {
         inputStream = new FileInputStream("inStream.txt");
         outputStream = new FileOutputStream("outStream.txt");
          
         int c;
         while ((c = inputStream.read()) != -1) {
            outputStream.write(c);           
         }
      } finally {
         if (inputStream != null) {
            inputStream.close();
         }
         if (outputStream != null) {
            outputStream.close();
         }
      }         
    }
}
```

### Đọc ghi file sử dụng Character Stream

- Có rất nhiều class Character Stream, để hình dung Character Stream hoạt động như thế nào, chúng ta sẽ tập trung vào FileReader và FileWriter.

```java
public class CopyFileCharacter {
    public static void main(String [] args) throws IOException {
      FileReader in = null;
      FileWriter out = null;
 
      try {
         in = new FileReader("input.txt");
         out = new FileWriter("output.txt");
          
         int c;
         while ((c = in.read()) != -1) {
            out.write(c);           
         }
      }finally {
         if (in != null) {
            in.close();
         }
         if (out != null) {
            out.close();
         }
      }         
    }    
}
```

### Sử dụng Buffered Streams

- Các ví dụ trên không sử dụng Buffered Streams, điều này có nghĩa là việc đọc và xuất dữ liệu được thực hiện trực tiếp dưới quyền điều khiển của hệ điều hành, gây lãng phí thời gian và tài nguyên. Để giảm thiểu những trên, Buffered Streams đã được sinh ra.

- Buffered Streams được sử dụng để tăng tốc độ hoạt động I/O, bằng cách đơn giản là tạo ra một khoảng nhớ đệm với kích thước cụ thể nào đó. Vì vậy chúng ta không cần phải truy cập vào ổ đĩa cứng khi thực hiện I/O. Một chương trình có thể chuyển đổi từ không sử dụng buffered stream (Byte Stream và Chracter Stream sang sử dụng buffered stream bằng việc sử dụng ý tưởng Wrapping.
- Ta bổ sung thêm
```java
bufferIn = new BufferedInputStream(inputStream);
bufferOut = new BufferedOutputStream(outputStream); 
```

### Sử dụng Scanner

```java
Scanner sc = new Scanner(new File("myNumbers.txt"));
while (sc.hasNextLong()) {
    long aLong = sc.nextLong();
}
```