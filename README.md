# autograde
## Phương pháp
- B1: Tìm tọa độ của các ô vuông định hướng và ô tròn trả lời
- B2: Từ tọa độ, khoanh vùng và tìm ra ô tròn tương ứng với phần nào, câu bao nhiêu
## Hướng dẫn chạy file
### Chạy file đơn
- Chấm bài
```
python3 program.py grade file <tên_file_chấm> <tên_file_output>
```
- Xuất ảnh để kiểm tra
```
python3 program.py show file <tên_file_chấm> <tên_file_output> <tên_file_xuất_ảnh>
```
### Chạy trong một thư mục
- Chấm bài
```
python3 program.py grade dir <tên_thư_mục> <tên_file_output>
```
- Xuất ảnh để kiểm tra
```
python3 program.py show dir <tên_thư_mục> <tên_file_output> <thư_mục_chứa_ảnh_đích>
```
### File "debug.txt" 
File này được dùng để ghi ra tổng số ô tròn, sau khi đã chia tách và phân tích vị trí. Trước khi chạy với thư mục nên xóa hết dữ liệu trong file để dễ kiểm tra số ô tròn thu được từ mỗi bài.
- Nếu bài làm tô đúng quy cách, mỗi câu/ý của câu đều tô 1 ô tròn, thì tổng số ô tròn sẽ là 105.
- Con số "hợp lí" sẽ dao động trong khoảng [90,110] tùy thuộc chất lượng ảnh và việc xác định của thuật toán
- Nếu số ô tròn nhận được dưới 50, trừ trường hợp bài chỉ tô dưới 50 ô tròn thì nguyên nhân có thể là:
    - Xác định sai ô vuông => không tách được bài hoặc tách sai => việc nhận dạng vị trí ô tròn sai
    - Các bước tiền xử lí ảnh và xác định contours để tìm ô tròn gặp lỗi, gây nhận diện không đúng, đủ số ô tròn
- Nếu số ô tròn nhận được trên 110, trừ trường hợp bài thi tô quá nhiều thì nguyên nhân có thể là:
    - Các phần chữ, số trong bài hoặc ô vuông bị nhận dạng nhầm thành ô tròn
    - Các ô tròn không được tô bị nhận dạng nhầm thành ô tròn được tô
