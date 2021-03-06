英文部分来自书籍 SPA design and architecure, 仅供参考，请勿商用.
1.传统的应用程序架构，参考images目录中的figure1.1
  Figure 1.1 shows a large web application that uses a traditional server-side design.
With this design, each request for a new view (HTML page) results in a round-trip to the server. When fresh data is needed on the client side, the request is sent to the server side. On the server side, the request is intercepted by a controller object inside the presentation layer. The controller then interacts with the model layer via the ser- vice layer, which determines the components required to complete the model layer’s task. After the data is fetched, either by a data access object (DAO) or by a service agent, any necessary changes to the data are then made by the business logic in the business layer.Control is passed back to the presentation layer, where the appropriate view is cho- sen. Presentation logic dictates how the freshly obtained data is represented in the selected view. Often the resulting view starts off as a source file with placeholders, where data is to be inserted (and possibly other rendering instructions). This file acts as a kind of template for how the view gets stamped whenever the controller routes a request to it.
After the data and view are merged, the view is returned to the browser. The browser then receives the new HTML page and, via a UI refresh, the user sees the new view containing the requested data.
                      
2.SPA的应用程序架构中，参考images目录中的figure1.2
Figure 1.2 demonstrates how this design could look as an SPA. Notice what has hap- pened with the presentation layer and our transactions.
Moving the process for creating and managing views into the UI decouples it from the server. From an architectural standpoint, this gives the SPA an interesting advan- tage. Unless you’re doing partial rendering on the server, the server is no longer required to be involved in how the data is presented.
The overall SPA design is nearly the same as the traditional design. The key changes are as follows: no full browser refreshes, the presentation logic resides in the client, and server transactions can be data-only, depending on your preference for data rendering.

3.SPA Shell, 参考images目录中的figure1.3 
  the shell is minimal in structure and often contains a single, empty DIV tag that will house the rest of the application’s content. You can think of this shell HTML file as the mother ship and the initial container DIV as the docking bay.
  ## The “pages” of the application aren’t pages at all, at least not in the traditional sense. As the user navigates, the parts of the screen that appear to be pages are actually inde- pendent sections of the application’s content, called views. 
  page concept 参考images目录中的1.4
  view concept 参考images目录中的1.5
4. 为什么会出现SPA呢？
  SPAs are at the forefront of this user-experience revolution. 
  1）Renders like a desktop application, but runs in a browser
  2）Decoupled presentation layer—As mentioned previously, the code that governs how the UI appears and how it behaves is kept on the client side instead of the server. This leaves both server and client as decoupled as possible. The benefit here is that each can be maintained and updated separately.
  3）Faster, lightweight transaction payloads
  4）Less user wait time—In today’s web-centric world, the less time a user has to wait for the page to load, the more likely the person is to stay on the site and return in the future. Because the SPA loads with a shell and a small number of support- ing files and then builds as the user navigates, application startup is perceived as being quick. As the previous points state, screens render quickly and smoothly, and transactions are lightweight and fast. These characteristics all lead to less user wait time. A study by Walmart that was published in Web Performance Today1 indicated that for every 100 ms of perfor- mance improvement, incremental revenue grew by up to 1%.
5. in an SPA, the application is broken into independent sections, or views. So you’ll no longer create entire pages in which common elements, such as a header or a main menu, are repeated. Even the common sec- tions are views in an SPA. You’ll also have to stop thinking about the layout of individual pages and start thinking in terms of view placement in the available real estate of the screen. As it turns out, this is easy after you get the hang of it. Global lay- out areas, such as a main menu, remain fixed throughout the user experience. Shared areas of the screen, such as the center content well, are reused by the application to swap the various views (as well as entire regions) during user navigation.To the end user, though, the application can look exactly like a traditional web application. As figure 1.11 illustrates, it can have a header, a sidebar, or any other typi- cal web-page element.

6. 第2章介绍MV*框架，第3章介绍模块编程，第4章介绍SPA路由，第5章介绍SPA组合和布局。第6章介绍模块间通信，采用pub/sub模式，使得模块可以广播通信。第7章介绍服务端通信,引入promise和RESTful service。第8章引入单元测试。第9章介绍前端自动化。

7.Some of the benefits of an SPA include a desktop-like feel, a decoupled presen- tation layer, faster and lighter payloads, less user wait time, and easier code maintenance.