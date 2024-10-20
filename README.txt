Các source code có thể chạy trên Colab Pro.

Lưu ý về môi trường trên colab, các package v.v được cập nhật và thay đổi theo thời gian nên kết quả khi chạy lại ở hiện tại có thể sẽ không giống hoàn toàn so với số liệu thực nghiệm trước đây. 



NOTE:
Ở cách tiếp cận đề xuất, gần đây em có nhận ra một nhược điểm trong việc thiết kế đó là chưa đảm bảo được độ tương quan giữa các lần inference option khác nhau. 

Ví dụ một trường hợp có thể xảy ra:
-  Option A (Đáp án đúng):
	+ logit "yes" = 10
	+ logit "no" = 1
	=> Yes probability cao

-  Option B (Đáp án sai):
	+ logit "yes" = 20
	+ logit "no" = 40
	=> Yes probability thấp

=> STL("yes") suy luận đáp án là B (sai).

Có thể cải thiện bằng scale các giá trị yes logit dựa trên một giá trị, nguyên tắc nào đó HOẶC thay đổi công thức đưa ra dự đoán; để tạo được mối tương quan giữa các lần inference prompt của các option khác nhau.
