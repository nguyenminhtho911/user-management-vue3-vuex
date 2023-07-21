### -- chức năng add user
- **b1** : xử form
- **b2** : xử lý sự kiện click submit -> dispatch action lên store
- **b3** : xử lý action -> mutation ( update state )
- **b4** : lấy state từ store về để show lên màn hình

### -- chức năng remove user
- **b1** : xác định component có nút xóa ( UserItem )
- **b2** : xử lý sự kiện click nút xóa -> dispatch action ( gửi kèm id )
- **b3** : lên vuex ( store ) xử lý action -> commit mutation ( xóa và cập nhật lại state )
- **b4** : lấy state từ store về để show lên màn hình

---

### Bổ sung:

#### Modal
- Cha --> truyền xuống Modal con: `1 biến` để mở và `1 hàm` để khi cần thì nó đóng

#### Edit user
- Click show `Modal` -> truyền vào `userInfo` (user hiện tại trong listUser)
- Khi **submit form** lấy `userInfo` này để nhận biết là `update` --> gọi `action update`

#### Phân biệt `form` khi `add` hoặc `edit`
- Add thì handle bình thường
- **Edit** --> khi `form` `created` check có `userInfo` truyền vào ==> đang edit
  + Cập nhật `userInfo` vào form

#### Search
- submit gọi `action search` -> commit -> getter ->  `fillter` user tương ứng với `termSearch`
- `component` sẽ lấy `userListBySearchName` render ra.

