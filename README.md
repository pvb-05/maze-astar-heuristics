# Maze Astar Heuristics 🗺️

> Đồ án Sinh viên Khoa Công nghệ Thông tin  
> Tên đề tài: Nghiên cứu và so sánh các heuristic trong thuật toán A* để giải mê cung

Một dự án Python mô phỏng việc giải quyết mê cung bằng thuật toán A* (A-Star), kết hợp với các phương pháp heuristic khác nhau như Manhattan, Euclidean và Chebyshev. Dự án không chỉ tìm đường đi ngắn nhất mà còn trực quan hóa kết quả bằng ảnh PNG để minh họa lời giải.

## 1. Mục tiêu dự án

- Tìm đường đi từ điểm bắt đầu A đến điểm đích B trong mê cung.
- So sánh hiệu quả của các heuristic khác nhau trong thuật toán A*.
- Hỗ trợ điều khiển hướng di chuyển theo các kiểu: 4 hướng hoặc 8 hướng (cho phép đi chéo).
- Xuất kết quả trực quan dưới dạng hình ảnh `solution.png`.

## 2. Tính năng chính

- Thuật toán A* giải mê cung hiệu quả.
- Hỗ trợ 3 heuristic:
  - Manhattan
  - Euclidean
  - Chebyshev
- Tự động vẽ đường đi đã tìm được lên ảnh.
- Hiển thị thông tin thống kê như:
  - số trạng thái đã khám phá
  - chi phí đường đi
  - thời gian chạy
- Có thể tạo mê cung ngẫu nhiên bằng script riêng.

## 3. Cấu trúc thư mục

```text
maze-astar-heuristics/
├── README.md
├── maze.py
├── generate.py
├── mazeA.txt
├── mazeB.txt
├── mazeC.txt
├── mazeD.txt
├── requirement.txt
├── solution.png
└── mazerandom.txt   # được sinh ra khi chạy generate.py
```

## 4. Công nghệ sử dụng

- Python 3
- Thư viện Pillow để xử lý và xuất ảnh

## 5. Yêu cầu môi trường

Trước khi chạy dự án, hãy cài đặt các dependency:

```bash
pip install -r requirement.txt
```

## 6. Cách chạy chương trình

### 6.1. Chạy giải mê cung

```bash
python maze.py <file_maze> <heuristic>
```

Ví dụ:

```bash
python maze.py mazeA.txt manhattan
python maze.py mazeB.txt euclidean
python maze.py mazeC.txt chebyshev
```

### 6.2. Tạo mê cung ngẫu nhiên

```bash
python generate.py <width> <height>
```

Ví dụ:

```bash
python generate.py 10 10
```

Sau khi chạy, file `mazerandom.txt` sẽ được tạo tự động.

### 6.3. Xem kết quả

- Kết quả đường đi sẽ được in ra terminal.
- Ảnh lời giải sẽ được lưu vào file `solution.png`.

## 7. Định dạng file mê cung

File maze được lưu dưới dạng văn bản, trong đó:

- `A`: điểm bắt đầu
- `B`: điểm kết thúc
- `#`: tường
- khoảng trắng: ô trống

Ví dụ:

```text
##    #
## ## #
#B #  #
# ## ##
      ##
A######
a
```

## 8. Thuật toán sử dụng

Dự án triển khai thuật toán A* theo công thức:

- `f(n) = g(n) + h(n)`
- `g(n)`: chi phí từ điểm bắt đầu đến nút hiện tại
- `h(n)`: ước lượng khoảng cách còn lại đến đích (heuristic)

Các heuristic được triển khai gồm:

- Manhattan:
  - phù hợp cho di chuyển theo 4 hướng
- Euclidean:
  - đo khoảng cách thực tế theo đường chéo
- Chebyshev:
  - hữu ích khi cho phép di chuyển chéo

## 9. Kết quả mong đợi

Khi chạy thành công, chương trình sẽ:

1. Đọc mê cung từ file.
2. Tìm đường đi tối ưu bằng A*.
3. In sơ đồ đường đi ra console.
4. Lưu hình ảnh lời giải vào `solution.png`.
5. Hiển thị thống kê về tình trạng khám phá và thời gian thực thi.

## 10. Một số lưu ý

- Nếu dùng heuristic Euclidean hoặc Chebyshev, chương trình có thể hỏi xem bạn có muốn bật tính năng đi chéo hay không.
- Khi không tìm thấy đường đi, chương trình sẽ thông báo lỗi hoặc kết thúc với thông báo "No solution!".
- Dự án này phù hợp cho mục đích học tập và demo về thuật toán tìm đường trong trí tuệ nhân tạo.

## 11. Liên hệ

Tác giả: Bac Phan  
Email: phanvanbac15112005@gmail.com

## 12. Ghi chú

Đây là một dự án học tập đơn giản, tập trung vào việc hiểu và triển khai thuật toán A* trong bài toán giải mê cung. Nếu bạn muốn mở rộng, có thể phát triển thêm các tính năng như:

- hỗ trợ nhiều loại mê cung hơn
- trực quan hóa quá trình duyệt trạng thái
- so sánh hiệu suất giữa các heuristic qua từng bài toán
- xây dựng giao diện đồ họa bằng PyGame hoặc Tkinter

---

Nếu bạn muốn, mình có thể tiếp tục giúp bạn:
- viết thêm mô tả chi tiết theo kiểu báo cáo đồ án
- chỉnh sửa README sang phiên bản chuyên nghiệp hơn
- tạo file `requirements.txt` hoặc `LICENSE`
- viết phần "Mô tả thuật toán A*" theo chuẩn báo cáo khoa học
