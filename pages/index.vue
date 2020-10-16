<template>
  <div>
    <site-card-group :data="sites" />
    <social-card-group :data="socials" />
  </div>
</template>

<script>
export default {
  data: () => ({
    sites: [
      {
        title: '博客',
        src: './images/aura.jpg',
        href: 'https://bun.plus/',
        description:
          '欢迎访问我的个人博客。这里的文章包含了前后端软件开发技术、精品软件推荐等内容。让我们一起学习、成长。'
      },
      {
        title: '作品',
        src: './images/snow_mountain.jpg',
        href: 'https://bun.dev/',
        description:
          '这里有我开发的开源小作品，如果能帮到你那真是太好了。如果遇上bug别忘了反馈，若是能贡献代码那更是太棒了！'
      },
      {
        title: '关于我',
        src: './images/danhuang.jpg',
        href: 'https://nzc.me/',
        description: '如果对我感兴趣，可以进一步了解……'
      }
    ],
    socials: [
      {
        title: '新浪微博',
        name: '@呼呼小笼包',
        color: 'red',
        icon: 'mdi-sina-weibo',
        href: 'https://weibo.com/201274727'
      },
      {
        title: '微信公众号',
        name: 'bundev',
        color: 'green',
        icon: 'mdi-wechat',
        href: './images/bundev_wechat_qr.png'
      },
      {
        title: 'GitHub',
        name: 'huhubun',
        color: 'rgb(43,49,55)',
        icon: 'mdi-github',
        href: 'https://github.com/huhubun'
      },
      {
        title: 'LOFTER',
        name: '小笼包在这里',
        color: 'light-green darken-3',
        icon: 'mdi-alpha-l-circle-outline',
        href: 'https://huhubun.lofter.com/'
      }
    ]
  })
}
</script>
