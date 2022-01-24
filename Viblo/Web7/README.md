# [Web7](https://ctf.viblo.asia/puzzles/web7-qwevvyc7qkq)

> http://172.104.49.143:1312

---

Mình nhận được một đường dẫn. Kiểm tra source thì không thấy có gì đặc biệt:

> ![](1.png)

Khi vào đường dẫn `robots.txt` thì mình nhận được một đường dẫn `disallow` là `index.abc`:

> ![](2.png)

Mình vào đường dẫn đó thì thấy được đoạn code:

> ![](3.png)

Đoạn code này yêu cầu mình truyền vào 1 param `password`. Hàm `ereg` dùng để kiểm tra dữ liệu truyền vào có phải chỉ gồm các chữ cái và số không. Tuy nhiên sau đó lại yêu cầu giá trị param `password` lại cần có `^_^` nên mình nghĩ bài này yêu cầu khai thác vào cách bypass hàm `ereg`. Mình tra google xem có cách nào bypass hàm này không. Và kết quả mình tìm được một bài viết nói về việc này:

> ![](4.png)

Truyền vào param với NULL byte: http://172.104.49.143:1312/?password=aaaa%00^_^ mình thu được flag:

> ![](5.png)

**Flag{POISON_NULL_BYTE}**
