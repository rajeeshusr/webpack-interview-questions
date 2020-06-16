# Webpack Interview Questions with Answer

### Table of Contents

| No. | Questions |
| --- | -------------------------------------------------------------------------------------------------------------- | |
| 1 | [What is Webpack?](#what-is-webpack) |
| 2 | [What are the major features of React?](#what-are-the-major-features-of-webpack) |
| 3 | [Important plugins using in Webpack?](#important-plugins-using-in-Webpack) |
| 4 | [What is the Dependency Graph in Webpack?](#what-is-the-dependency-graph-in-webpack) |

1. ### What is Webpack?

   Webpack is a build tool that puts all of your assets, including Javascript, images, fonts, and CSS, in a dependency graph. Webpack lets you use **require()** in your source code to point to local files, like images, and decide how they're processed in your final Javascript bundle, like replacing the path with a URL pointing to a CDN.

**[⬆ Back to Top](#table-of-contents)**

2. ### What are the major features of Webpack?

   Webpack and static assets in a dependency graph offers many benefits. Webpack is the main build tool adopted by the React community.

   The major features of Webpack are:

   - Dead asset elimination. This is killer, especially for CSS rules. You only build the images and CSS into your dist/ folder that your application actually needs.
   - Easier code splitting. For example, because you know that your file Homepage.js only requires specific CSS files, Webpack could easily build a homepage.css file to greatly reduce initial file size.
   - You control how assets are processed. If an image is below a certain size, you could base64 encode it directly into your Javascript for fewer HTTP requests. If a JSON file is too big, you can load it from a URL. You can **require('./style.less')** and it's automatically parsed by Less into vanilla CSS.
   - Stable production deploys. You can't accidentally deploy code with images missing, or outdated styles.
   - Webpack will slow you down at the start, but give you great speed benefits when used correctly. You get hot page reloading. True CSS management. CDN cache busting because Webpack automatically changes file names to hashes of the file contents, etc.

**[⬆ Back to Top](#table-of-contents)**

3. ### Important plugins using in Webpack?

   - CommonsChunkPlugin - creates a separate file (known as a chunk), consisting of common modules shared between multiple entry points.
   - DefinePlugin - allows you to create global constants which can be configured at compile time.
   - HtmlWebpackPlugin - simplifies creation of HTML files to serve your webpack bundles.
   - ExtractTextWebpackPlugin - Extract text from a bundle, or bundles, into a separate file.
   - CompressionWebpackPlugin - Prepare compressed versions of assets to serve them with Content-Encoding.

**[⬆ Back to Top](#table-of-contents)**

4. ### What is the Dependency Graph in Webpack?

   Dependency means one file depends on another file. This allows webpack to take non-code assets, such as images or web fonts, and also provide them as dependencies for your application.

   Webpack lets you use require() on local "static assets":

   **<img src={ require('../../assets/logo.png') } />**
   When webpack processes your application, it starts from a list of modules defined on the command line or in its config file. Starting from these entry points, webpack recursively builds a dependency graph that includes every module your application needs, then packages all of those modules into a small number of bundles - often, just one - to be loaded by the browser.

   The require('logo.png') source code never actually gets executed in the browser (nor in Node.js). Webpack builds a new Javascript file, replacing require() calls with valid Javascript code, such as URLs. The bundled file is what's executed by Node or the browser.

**[⬆ Back to Top](#table-of-contents)**
