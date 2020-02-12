# todo

- [x] nuxt.js入れる
- [x] netlifyにデプロイ
- [x] vue.js復習
- [x] nuxt上でvue.jsだけで簡単に実装する（nuxtの詳細を知りたくないのでindexだけで何か動かす）
- [ ] コンポーネント分割してみる
- [ ] vuex学ぶ
- [ ] vuexでリファクタする

## はまり

- <https://stackoverflow.com/questions/6632191/how-to-revert-initial-git-commit>
- vueコンポーネントとvueインスタンスは違う、vueコンポーネントはdataは関数にしないとthisで参照できない
  - <https://jp.vuejs.org/v2/guide/single-file-components.html>
  - <https://jp.vuejs.org/v2/guide/components.html>
- テンプレート構文は省略記法がいくつかある
  - <https://jp.vuejs.org/v2/guide/syntax.html>
- pagesにある_id.vueみたいなのは何？
  - ルーティング上クエリパラメータになっている場合はこうなるらしい
- pagesとcomponentsの違い
  - pagesはルーティングの設定対象になる
  - APIコールはpagesだけがするらしい
    - とはいえvuexのstore経由で呼ぶならcomponents内でも呼ぶ
    - this.$firebase.　みたいなのも別にcomponentsからできる
- filters何
- propsでfunctionを渡す時はv-bindで渡さないといけないみたい
  - <https://medium.com/@jariwalamahek/how-to-pass-function-as-a-prop-in-vue-b7b0040260ba>
- <Component></Component>と<Component/>は意味が違う？
- Vuexを利用せずに親子関係を持たないコンポーネント同士で通信する
  - <https://www.ie-kau.net/entry/communication_between_components_without_parent-child_relation_in_vuejs>