# How to Build A Spin Application with React

I recently built a template for building Spin Applications with React for people who are willing to use React to build their very first Spin Application. Currently, you only have one alternative to using React to build your first Spin application: using the Spin [Next Template](https://github.com/radu-matei/spin-nextjs) to use Next JS. This has the unique benefit of letting React developers use Spin as well.   

You may be in awe of why I’m talking about this. I’m a big fan of React, and I recently implemented a template that lets you build a Spin application with React, and I’m loving it. not because I built it myself, but because I love the fact that I did this one because creating microservice applications with React is not so easy to do. Normally, building microservice applications with React will give you issues during debugging, and there will also be inter-process communication, but while building with Spin, you’ll never encounter any of these issues.

## **Oh, in case you forgot...**

Spin is a framework used for building and running microservice applications with WebAssembly components. With Spin, it’s pretty much accessible, scalable, and secure when it comes to running microservices. Even though Spin can be used with different technologies like Rust, Go, JavaScript, and many more, this article is focused on building a Spin application with React.

In this case, we will be building a QR code generator with Spin and React. It’s not exactly done the normal way, but there are also some things you’ll learn from this article:

* You’ll learn how to use the Spin React Template and set it up with the Spin CLI.
    
* You’ll learn how to build a QR code generator with Spin and React.
    
*  You’ll also learn about the structure of the template.
    

## **Getting Started** 

First, make sure you have the Spin CLI installed. If you don’t, you can follow the steps [here](https://developer.fermyon.com/spin/install). After doing that, install the template with the Spin CLI:  

```bash
$ spin templates install --git https://github.com/coderoflagos/spin-reactjs.git

Copying remote template source

Installing template spin-reactjs...

Installed 1 template(s)


+------------------------------------------------------------------------+

| Name           Description                                             |

+========================================================================+

| spin-reactjs   Build your front-end application using reactjs and Spin |

+------------------------------------------------------------------------+

```

After doing this, now create a project based on the template you installed.

```bash
$ spin new spin-reactjs my-react-app
# your new application has been created in the my-react-app directory
```

Next, navigate to the application’s directory by running `cd my-react-app`, and then run the `npm install` command in the terminal. You can now open VSCode by using the `code .` command. Here’s what the project directory will look like:

![](https://lh5.googleusercontent.com/4gh55Iuw8RfWb6TsQOTYCojLZKPpMGfM27P0xgIgUTYo8hKelNeWudce38k74wT7cnULwK_1BJmbQarz_kcCQSiHco_2S8CjlL8KFAAPgAeh4C82bm0WWw6iryBoO88YUQcmpFXKhGHU0owFTQjfVz4 align="left")

Just as you can see above, we have the `spin.toml` file—the file for Spin’s configuration. It also has a hidden configuration in the directory.

Now, create a `components` directory under the `src` directory. Now, under the `components` directory, create a `QrCode.js` file in it. 

Copy and paste the following code into your **QrCode.js** file:

```javascript
import { useState, useRef } from "react";

import { QRCodeCanvas } from "qrcode.react";

const QrCode = () => {

 const [url, setUrl] = useState("");

 const qrRef = useRef();

 const downloadQRCode = (e) => {

   e.preventDefault();

   let canvas = qrRef.current.querySelector("canvas");

   let image = canvas.toDataURL("image/png");

   let anchor = document.createElement("a");

   anchor.href = image;

   anchor.download = qr-code.png;

   document.body.appendChild(anchor);

   anchor.click();

   document.body.removeChild(anchor);

   setUrl("");

 };

 const qrCodeEncoder = (e) => {

   setUrl(e.target.value);

 };

 const qrcode = (

   <QRCodeCanvas

     id="qrCode"

     value={url}

     size={300}

     level={"H"}

   />

 );

 return (

   <div className="qrcode__container">

     <div ref={qrRef}>{qrcode}</div>

     <div className="input__group">

       <form onSubmit={downloadQRCode}>

         <label>Enter URL</label>

         <input

           type="text"

           value={url}

           onChange={qrCodeEncoder}

         />

         <button type="submit" disabled={!url}>

           Download QR code

         </button>

       </form>

     </div>

   </div>

 );

};

export default QrCode;

```

Firstly, the library `qrcode.react` is a component to generate QR codes for rendering to the DOM. So, you need to install the dependency command with the command below:

```bash
npm install qrcode.react
```

Next, you can see the `downloadQRCode` function; it works with the Download QR Code button too. 

You can read [this article](https://hackernoon.com/how-to-build-a-qr-code-generator-in-react) to learn more about this code. 

Create a stylesheet `styles.css` in the `src` directory; now copy and paste this code in your `styles.css` file:

```css
*,

*:before,

*:after {

 margin: 0;

 padding: 0;

 box-sizing: border-box;

}

:root {

 --font-color: 230 35% 7%;

}

body {

 color: hsl(var(--font-color));

}

img {

 max-width: 100%;

 display: block;

}

.section {

 padding: 2em 0;

 display: flex;

 min-height: 100vh;

 align-items: center;

}

.container {

 margin-inline: auto;

 max-width: 75rem;

 width: 85%;

}

.input__group {

 display: flex;

 margin-top: 2em;

}

input {

 width: 100%;

 padding: 1em 0.75em;

 border: 1px solid #444343;

 border-radius: 3px;

 margin-bottom: 2em;

 margin-top: 0.75em;

}

button {

 border: unset;

 background: gray;

 padding: 1em 0.75em;

 cursor: pointer;

 font-weight: bold;

}

@media screen and (min-width: 768px) {

 .section {

   padding: 0;

 }

 input {

   margin: 0;

 }

 .qrcode__container {

   display: flex;

   align-items: center;

 }

 .input__group {

   margin-left: 3em;

 }

 input {

   margin-bottom: 2em;

   margin-top: 0.75em;

   font-size: 1rem;

 }

}
```

Next, import whatever is in the `QrCode.js` file to the `App.js` file:

```javascript
import QrCode from "./components/QrCode";

import "./styles.css";

export default function App() {

 return (

   <div className="section container">

     <QrCode />

   </div>

 );

}
```

Once again, you can read this article to learn more about the code. After doing all these when you run the `spin up && spin build` command in your terminal, you should have this:

![](https://lh6.googleusercontent.com/RvixGP-uHTkVVlx6g4zavAXgAikTcEAlozmmvL-qKL66rGlc4cDqQ5dTcbXr4A58RP4XS2K0DC_6u-8xmcSi6L3D6qwIpfe-CNq3W9PTN8CTslIf0B47sblG843mY9Z7ejqvjwbAx7YhUKl_ekAYTRQ align="left")

  

## **Conclusion**

With this article, you’ve just learned how to build your very first React application that runs on Spin, and with this, things become pretty easy. This was built using the [Spin React JS Template](https://github.com/coderoflagos/spin-reactjs). This article is slightly related to [this one](https://hackernoon.com/how-to-build-a-qr-code-generator-in-react). I hope this turns out to be helpful - thanks for reading.