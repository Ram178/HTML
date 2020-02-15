<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <title>Html editor</title>
<style>
	* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}


.btn {
  position:absolute;
  top:0%;
  left:25%;
   padding: 0.4rem;
  width: 6rem;
  background: #999999;
  color: gold;
  font-size: 1rem;
  outline:none;
  cursor:pointer;
   height:8%;
}
.btn:hover{
   color:white;
   background: blue;
}


.main-editor {
  background:#D0ECE7;
  display: flex;
  width: 100%;
  top:7%;
  padding: 4rem;
  box-shadow:0 2px 3px black;
  position:fixed;
    height:110vh;
   justify-content: center;
    align-items: center;
  border: 7px solid #36383f;
}

.first {
  background-color: #ffffff;
  width: 50%;
  top:30%;
   overflow-x: hidden;
  overflow-y: auto;
  white-space: pre;
  box-shadow: 0 1px 1px rgb(22, 22, 22);
  outline: none;
  padding: 0.4rem;
  height: 90vh;
}

.second {
  background-color: rgb(255, 255, 255);
  width: 50%;
  overflow-y: auto;
  white-space: pre;
  right: 0;
  box-shadow: 0 1px 1px rgb(22, 22, 22);
  padding: 0.4rem;
  height: 90vh;
}
</style>
</head>
<body>
    <div class="main-editor" >
        <button class="btn">Run</button>
		<div style="font-size:25px;font-family:arial;" class="first" contenteditable>
        &#60html&#62
	   &#60head&#62
	  &#60body&#62
	 &#60h1&#62Hello World&#60/h1&#62
	 &#60/body&#62
	  &#60/head&#62
	  &#60/html&#62
        </div>
        <iframe class="second">
        </iframe>
    </div>

    <script>
	const first = document.querySelector(".first");
const iframe = document.querySelector("iframe");
const btn = document.querySelector("button");

btn.addEventListener("click", () => {
  var html = first.textContent;
  iframe.src = "data:text/html;charset=utf-8," + encodeURI(html);
});


	</script>
	
</body>
</html>
