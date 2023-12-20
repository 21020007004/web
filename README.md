### 前端各个文件的作用
1. home.vue:是首页的前端展示，这个Vue组件包含了一个轮播图区域和一个日历区域，使用了Element UI库的 el-carousel 和 el-calendar 组件。
2. layout.vue:这个 Vue.js 组件使用了 Element UI 的布局容器 (el-container)，其中包含头部 (el-header)、侧边栏 (el-aside) 和主体内容 (el-main) 区域。头部和侧边栏分别引入了名为 Header 和 NavMenu 的组件，而主体内容区域则使用 Vue Router (router-view) 动态展示不同的页面组件。（Vue Router 是 Vue.js 的官方路由管理器。它和 Vue.js 核心深度集成，允许你以声明式的方式构建单页面应用 (SPA)。Vue Router 能够通过定义路由规则，将不同的视图组件映射到对应的 URL。这样，在用户访问不同的 URL 时，页面可以实现切换，而不需要重新加载整个页面。router-view 是 Vue Router 中的一个组件，用于显示当前路由匹配到的组件内容。在上述代码中，<router-view></router-view> 的作用是在 el-main 区域显示当前路由对应的组件内容。当用户点击导航链接或通过其他方式改变了路由，Vue Router 会根据定义的路由规则，找到匹配的组件并将其渲染到 router-view 中）
3. 其中layout.vue调用了，两个组件el-header和el-aside，这两个组件在component文件夹下，el-header组件实现的功能，修个密码和退出登录
   ![image](https://github.com/21020007004/web/assets/128390031/0def4963-5bdd-4182-be78-022d4e177ec0)
   el-aside组件实现的功能是：左侧菜单栏
   ![image](https://github.com/21020007004/web/assets/128390031/11da6209-d22b-4cc2-bb84-9c30e5bb762b)
4. 左侧工具栏主要包括四个部分，首页、人员管理、课程审批、教学安排。
5. 其中人员管理包括学生管理和教师管理：在member文件夹下，
