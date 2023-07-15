# Advanced Python Programming (Lập Trình Python Nâng Cao)

## Virtual Environment (môi trường ảo)
 Một môi trường ảo là một môi trường Python cô lập cho phép bạn cài đặt và quản lý các gói riêng biệt khỏi cài đặt Python hệ thống trên máy tính của bạn.  
### Tạo một venv (python 3)
`python -m venv myvenv`
- "python": là lệnh để gọi trình thông dịch (interpreter) Python
- "-m": là một tùy chọn trong dòng lệnh Python, viết tắt của "module", cho biết Python sẽ chạy một module cụ thể như một script
- "venv": là tên của module mà chúng ta muốn chạy, module "venv" là một module tích hợp sẵn trong Python cung cấp chức năng để tạo và quản lý môi trường ảo
- "myvenv" là tên mà bạn muốn đặt cho môi trường ảo mới. Bạn có thể thay thế "myvenv" bằng bất kỳ tên nào bạn muốn cho môi trường ảo của mình

- Khi bạn chạy lệnh "python -m venv myvenv", Python sẽ sử dụng module "venv" để tạo một môi trường ảo mới có tên là "myvenv". Môi trường ảo này sẽ được tạo ra trong thư mục hiện tại của bạn. Nó sẽ bao gồm một bản sao của trình thông dịch Python và một số thư mục và tệp tin khác cần thiết để chạy một môi trường Python độc lập.

- Môi trường ảo cho phép bạn cài đặt các gói và dependencies riêng biệt cho từng dự án của bạn. Khi bạn kích hoạt môi trường ảo này (bằng cách sử dụng các lệnh tương ứng trên hệ điều hành của bạn), Python sẽ sử dụng trình thông dịch và các thư viện từ môi trường ảo này thay vì từ cài đặt Python hệ thống của bạn. Điều này giúp đảm bảo rằng các gói và dependencies chỉ tồn tại trong phạm vi môi trường ảo và không ảnh hưởng đến các dự án khác trên máy tính của bạn.
### Kích hoạt một môi trường ảo đã tạo
 - Bằng cách sử dụng lệnh tương ứng cho hệ điều hành của bạn
 - Ví dụ: 
   - `source myvenv/bin/activate` trên các hệ điều hành dựa trên Unix 
   - hoặc `myvenv\Scripts\activate` trên Windows
 - Sau khi kích hoạt, các lệnh Python hoặc cài đặt gói phụ sau đó sẽ được thực hiện trong phạm vi của môi trường ảo, đảm bảo rằng dự án của bạn có môi trường Python cô lập riêng biệt.
### Thoát môi trường ảo
- Để tắt (deactivate) một môi trường ảo Python, bạn cần thực hiện các bước tương ứng với hệ điều hành bạn đang sử dụng.
- Trên các hệ điều hành dựa trên Unix (như Linux hoặc macOS), sử dụng lệnh sau để tắt môi trường ảo: *`deactivate`*
- Trên hệ điều hành Windows, sử dụng lệnh sau để tắt môi trường ảo: *`myvenv\Scripts\deactivate.bat
`*
- Trong đó, myvenv là tên của môi trường ảo của bạn. Nếu bạn đã đặt tên khác cho môi trường ảo, hãy thay thế myvenv bằng tên tương ứng.

- Khi bạn chạy lệnh deactive, môi trường ảo sẽ bị tắt và bạn sẽ trở lại môi trường Python hệ thống của bạn. Các gói và dependencies của môi trường ảo sẽ không còn được sử dụng và các lệnh Python sẽ trở lại sử dụng các cài đặt Python hệ thống.

### Các tips khi làm việc với môi trường ảo
- Nâng cấp **pip** (thông thương pip được nâng cấp liên tục): `pip install --upgrade pip`
- Cài đặt một package: `pip install <tên package>`, ví dụ: `pip install requests`
- Kiểm tra các package đã cài đặt trong môi trường ảo này: `pip freeze`
- Hiển thị thông tin của 1 package: `pip show <tên package>`
- Khi chạy python project, phải chọn trình thông dịch (interpreter) tương ứng với môi trường ảo đã tạo (*VS Code ở góc dưới bên phải*)
- Thường project python có file **requirements.txt**, là nơi chứa thông tin về những package mà project cần để chạy được, để khi cần triển khai hay cài lại môi trường ảo có thể cài đặt các package cần thiết một cách nhanh chóng. Bạn có thể chỉ định tên `package` hoặc tên với version `package==version` trong file **requirements.txt**. Để cài đặt các package trong file **requirements.txt**, chạy lệnh: `pip install -r requirements.txt`
- Bên cạnh đó, python project cũng có file **requirements-dev.txt** dùng cho mục đích phát triển như các package để test như pytest, black, flake8, ...