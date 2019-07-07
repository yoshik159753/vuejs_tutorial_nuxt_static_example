<!--
nuxt.js ではサーバサイドレンダリングを無効化することもできる。
その場合には次のコマンドのように `--spa` を指定する。
`npm run dev -- -spa`
-->

<template>
  <h2>{{ title }}</h2>
</template>

<script>
export default {
  // asyncData は Nuxt.js が提供する Vue.js のコンポーネントオプション。
  // 非同期なデータを取得するためのメソッドで、 **取得したデータを返すことで Vue.js の data にマージされる** 。
  async asyncData (context) {
    return await new Promise(resolve => {
      // バックエンドからのデータ取得をエミュレート
      setTimeout(() => {
        resolve({
          title: `このページは Nuxt 社のプロダクト情報のページです。(${ process.server ? 'サーバサイドレンダリング' : 'クライアントサイドレンダリング' })`
          // !!! 注) context.isServer は廃止されていた。今後は process.server !!!
          // title: `このページは Nuxt 社のプロダクト情報のページです。(${ context.isServer ? 'サーバサイドレンダリング' : 'クライアントサイドレンダリング' })`
        })
      }, 1000)
    })
  }
}
</script>
