---
home: true
heroImage: https://v1.vuepress.vuejs.org/hero.png
tagline: Documentation Of Bimabd Api
actionText: Quick Start →
actionLink: /guide/
features:
- title: Feature 1 Title
  details: Feature 1 Description
- title: Feature 2 Title
  details: Feature 2 Description
- title: Feature 3 Title
  details: Feature 3 Description
footer: Made by shibu deb polo with ❤️
---

Hello world from dhaka

~~~js
themeConfig: {
  repo: '',
  editLinks: false,
  docsDir: '',
  editLinkText: '',
  lastUpdated: false,
  nav: [
    {
      text: 'Guide',
      link: '/guide/',
    },
    {
      text: 'Config',
      link: '/config/'
    },
    {
      text: 'VuePress',
      link: 'https://v1.vuepress.vuejs.org'
    }
  ],
  sidebar: {
    '/guide/': [
      {
        title: 'Guide',
        collapsable: false,
        children: [
          '',
          'using-vue',
        ]
      }
    ],
  }
},
~~~