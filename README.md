<!doctype html>
<html>
<head>
<meta charset="UTF-8">
<title>Untitled Document</title>
<link rel="stylesheet" href="https://use.typekit.net/dlx5mik.css">

<style>:root {
  --smaller: .75;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html, body {
  height: 100%;
  margin: 0;
}

body {
  align-items: center;
  background-color: transparent;
  display: flex;
  font-family: "century-gothic";
  src: url('https://use.typekit.net/dlx5mik.css');
  font-size: 12pt;
}

.container {
  color: #FFFFFF;
  margin: 0 auto;
  text-align: center;
  font-size: 12pt;
  font-family: "century-gothic";
  src: url('https://use.typekit.net/dlx5mik.css');
}

h1 {
  font-weight: normal;
  letter-spacing: .125rem;
  text-transform: uppercase;
  font-size: 12pt;
  font-family: "century-gothic";
  src: url('https://use.typekit.net/dlx5mik.css');
}

li {
  display: inline-block;
  font-size: 12pt;
  list-style-type: none;
  padding: 1em;
  text-transform: uppercase;
  font-family: "century-gothic";
  src: url('https://use.typekit.net/dlx5mik.css');
}

li span {
  display: inline-block;
  font-size: 12pt;
  font-weight: 900;
}

.emoji {
  display: none;
  padding: 1rem;
}

.emoji span {
  font-size: 12pt;
  padding: 0 .5rem;
}

@media all and (max-width: 768px) {
  h1 {
    font-size: 12pt;
  }
  
  li {
    font-size: 12pt;
  }
  
  li span {
    font-size: 12pt;
  }
}
</style>
<script>
	(function () {
  const second = 1000,
        minute = second * 60,
        hour = minute * 60,
        day = hour * 24;

  //I'm adding this section so I don't have to keep updating this pen every year :-)
  //remove this if you don't need it
  let today = new Date(),
      dd = String(today.getDate()).padStart(2, "0"),
      mm = String(today.getMonth() + 1).padStart(2, "0"),
      yyyy = today.getFullYear(),
      nextYear = yyyy + 1,
      dayMonth = "09/27/",
      birthday = dayMonth + yyyy;
  
  today = mm + "/" + dd + "/" + yyyy;
  if (today > birthday) {
    birthday = dayMonth + nextYear;
  }
  //end
  
  const countDown = new Date(birthday).getTime(),
      x = setInterval(function() {    

        const now = new Date().getTime(),
              distance = countDown - now;

        document.getElementById("days").innerText = Math.floor(distance / (day)),
          document.getElementById("hours").innerText = Math.floor((distance % (day)) / (hour)),
          document.getElementById("minutes").innerText = Math.floor((distance % (hour)) / (minute)),
          document.getElementById("seconds").innerText = Math.floor((distance % (minute)) / second);

        //do something later when date is reached
        if (distance < 0) {
          document.getElementById("headline").innerText = "Days Left";
          document.getElementById("countdown").style.display = "none";
          document.getElementById("content").style.display = "inline block";
          clearInterval(x);
        }
        //seconds
      }, 0)
  }());// JavaScript Document</script>
</head>

<body>
<div class="container">
  <div id="countdown">
    <ul>
      <li><span id="days"></span> Days Left</li>
    </ul>
  </div>
  <div id="content" class="emoji">
  </div>
</div>
</body>
</html>
