
## Vuex + Vue3

### createNamespacedHelpers
> hàm heplper cho các module có đặc tính "namespaced"
- Ví dụ, nếu bạn có một module có tên là "user" với các actions là "login"
  + Khi dùng tên của action "login" sẽ được thay đổi thành "user/login" --> Tránh đụng độ giữa các module khác nhau.
 ```js
import { createNamespacedHelpers } from 'vuex';

const { mapState, mapGetters, mapActions, mapMutations } = createNamespacedHelpers('user');

export default {
  computed: {
    ...mapState(['username', 'isLoggedIn']),
    ...mapGetters(['getUserStatus']),
  },
  methods: {
    ...mapActions(['login', 'logout']),
    ...mapMutations(['setUsername']),
  },
};
 ```
- Ví dụ trên, các tên hàm như `login`, `logout`, `username`, `isLoggedIn` sẽ được thêm tiền tố là `user/` do đã sử dụng `createNamespacedHelpers('user')`.


### Proxy
> - Proxy để theo dõi và giám sát các thay đổi trên props được truyền vào
> - Proxy là một tính năng trong JavaScript cho phép bạn tạo một đối tượng giả mạo (proxy object) để bắt các thao tác trên đối tượng gốc.
