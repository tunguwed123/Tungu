
<!DOCTYPE html>
<html lang="hi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Creator AI Helper</title>
<style>
*{box-sizing:border-box}
body{
 margin:0;padding:20px;font-family:Arial,sans-serif;
 color:white;background:linear-gradient(135deg,#101126,#42156b);
 min-height:100vh
}
.container{max-width:600px;margin:auto}
h1{text-align:center;color:#e0bdff}
.sub{text-align:center;color:#ddd}
.card{
 background:#ffffff12;padding:18px;border-radius:18px;
 border:1px solid #ffffff25;margin:16px 0
}
label{display:block;margin:15px 0 7px}
input,select{
 width:100%;padding:13px;border:0;border-radius:10px;
 font-size:16px;background:#fff;color:#222
}
button{
 width:100%;padding:13px;margin-top:14px;border:0;
 border-radius:10px;background:#c18aff;color:#20102f;
 font-weight:bold;font-size:16px;cursor:pointer
}
#output{white-space:pre-wrap;line-height:1.7;overflow-wrap:anywhere}
.copy{background:#fff;color:#351252}
footer{text-align:center;color:#ccc;font-size:12px}
</style>
</head>
<body>
<div class="container">
<h1>✨ Creator AI Helper</h1>
<p class="sub">Reels aur Shorts ke liye Creator Toolkit</p>

<div class="card">
<label>वीडियो का विषय</label>
<input id="topic" placeholder="जैसे: गांव की जिंदगी">

<label>प्लेटफॉर्म</label>
<select id="platform">
<option>Instagram Reels</option>
<option>YouTube Shorts</option>
<option>Facebook Reels</option>
</select>

<label>भाषा</label>
<select id="language">
<option value="hi">हिंदी</option>
<option value="mix">Hinglish</option>
<option value="en">English</option>
</select>

<label>क्या बनाना है?</label>
<select id="kind">
<option value="all">पूरा Creator Pack</option>
<option value="title">वीडियो टाइटल</option>
<option value="caption">कैप्शन</option>
<option value="tags">हैशटैग</option>
<option value="ideas">वीडियो आइडिया</option>
<option value="thumbnail">थंबनेल टेक्स्ट</option>
</select>

<button onclick="generate()">✨ बनाओ</button>
</div>

<div class="card">
<h3>🎯 तुम्हारा रिजल्ट</h3>
<div id="output">अपना वीडियो विषय लिखकर बनाओ दबाओ।</div>
<button class="copy" onclick="copyResult()">📋 रिजल्ट कॉपी करो</button>
</div>

<footer>Free Creator Tool • Demo Version</footer>
</div>

<script>
function generate(){
 const topic=document.getElementById("topic").value.trim();
 const platform=document.getElementById("platform").value;
 const lang=document.getElementById("language").value;
 const kind=document.getElementById("kind").value;
 const out=document.getElementById("output");

 if(!topic){
  out.textContent="पहले वीडियो का विषय लिखो!";
  return;
 }

 const title=lang==="hi"
 ? [`${topic} की 5 खास बातें`,`क्या आप ${topic} के बारे में जानते हैं?`]
 : [`${topic} | Must Watch!`,`5 Things About ${topic}`];

 const captions=lang==="hi"
 ? [`आज की वीडियो: ${topic} ❤️ अपनी राय कमेंट में बताओ!`,
    `${topic} पसंद आया? दोस्तों के साथ शेयर करो ✨`]
 : [`Let's explore ${topic}! Share your thoughts below.`,
    `A new video about ${topic}. Like and share!`];

 const tags=["#Reels","#Shorts","#Creator",
  "#"+topic.replace(/[^\p{L}\p{N}]/gu,""),
  "#Video"];

 const ideas=[
 `${topic} के बारे में 3 रोचक बातें`,
 `${topic}: पहले और अब`,
 `${topic} से जुड़ी आम गलतियाँ`,
 `${topic} पर सवाल-जवाब`,
 `${topic} का एक मजेदार अनुभव`
 ];

 const thumbs=[
 `${topic.toUpperCase()}!`,
 "ये जरूर जानो!",
 "5 खास बातें",
 "क्या आप जानते हैं?"
 ];

 let result=`📱 ${platform}\n\n`;

 if(kind==="all"||kind==="title")
  result+="🎬 TITLE\n"+title.join("\n")+"\n\n";

 if(kind==="all"||kind==="caption")
  result+="✍️ CAPTION\n"+captions.join("\n\n")+"\n\n";

 if(kind==="all"||kind==="tags")
  result+="#️⃣ HASHTAGS\n"+tags.join(" ")+"\n\n";

 if(kind==="all"||kind==="ideas")
  result+="💡 VIDEO IDEAS\n• "+ideas.join("\n• ")+"\n\n";

 if(kind==="all"||kind==="thumbnail")
  result+="🖼️ THUMBNAIL TEXT\n"+thumbs.join("\n")+"\n\n";

 result+="Note: Ye preset suggestions hain, live trends nahi.";
 out.textContent=result;
}

async function copyResult(){
 const text=document.getElementById("output").innerText;
 try{
  await navigator.clipboard.writeText(text);
  alert("कॉपी हो गया!");
 }catch(e){
  const area=document.createElement("textarea");
  area.value=text;
  document.body.appendChild(area);
  area.select();
  document.execCommand("copy");
  area.remove();
  alert("रिजल्ट कॉपी करने की कोशिश पूरी हुई।");
 }
}
</script>
</body>
</html>
creater AI TOOL
m
