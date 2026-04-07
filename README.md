<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Lock In - Grade 7</title>
<style>
  :root{
    --dark:#06163f;
    --dark2:#0d2f7a;
    --light:#7fd3ff;
    --lav:#c8b5ff;
    --pink:#ff9ad5;
    --white:#f7fbff;
    --card:rgba(8,18,58,.92);
    --line:rgba(255,255,255,.14);
    --gold:#ffd86b;
  }

  *{box-sizing:border-box}
  html,body{margin:0;padding:0;scroll-behavior:smooth}
  body{
    font-family:"Segoe UI",Arial,sans-serif;
    color:var(--white);
    min-height:100vh;
    background:
      radial-gradient(circle at 15% 20%, rgba(255,154,213,.22), transparent 18%),
      radial-gradient(circle at 80% 10%, rgba(127,211,255,.20), transparent 18%),
      radial-gradient(circle at 75% 75%, rgba(200,181,255,.17), transparent 18%),
      linear-gradient(135deg,#04112f,#09215f 40%,#1c3f98 76%,#4558be 100%);
    overflow-x:hidden;
  }

  .sparkle-layer{
    position:fixed;
    inset:0;
    pointer-events:none;
    z-index:0;
    overflow:hidden;
  }
  .sparkle{
    position:absolute;
    width:4px;height:4px;
    border-radius:50%;
    background:white;
    box-shadow:0 0 12px white,0 0 20px rgba(255,255,255,.65);
    animation:twinkle 4s infinite ease-in-out;
  }
  .sparkle.big{
    width:7px;height:7px;
    background:linear-gradient(45deg,var(--light),var(--pink));
    box-shadow:0 0 16px var(--pink),0 0 24px var(--light);
  }
  @keyframes twinkle{
    0%,100%{transform:scale(.55);opacity:.28}
    50%{transform:scale(1.45);opacity:1}
  }

  .wrap{
    position:relative;
    z-index:1;
    max-width:1240px;
    margin:0 auto;
    padding:24px;
  }

  .card{
    background:var(--card);
    border:1px solid var(--line);
    border-radius:28px;
    box-shadow:0 18px 48px rgba(0,0,0,.38);
    padding:26px;
    margin-top:18px;
    backdrop-filter:blur(10px);
  }

  .hidden{display:none !important}
  .center{text-align:center}

  h1{
    margin:0 0 8px;
    font-size:3.3rem;
    line-height:1;
    letter-spacing:1px;
    background:linear-gradient(90deg,var(--light),var(--lav),var(--pink));
    -webkit-background-clip:text;
    background-clip:text;
    color:transparent;
  }
  .sub{
    color:#dce8ff;
    font-size:1.08rem;
    margin-bottom:18px;
  }
  .quote{
    max-width:760px;
    margin:18px auto 8px;
    font-size:1.35rem;
    line-height:1.6;
    font-weight:700;
  }
  .quote-author{
    color:var(--pink);
    margin-bottom:16px;
  }

  .inputRow{
    display:flex;
    justify-content:center;
    gap:10px;
    flex-wrap:wrap;
    margin-top:16px;
  }
  input[type="text"]{
    width:min(520px,90%);
    padding:14px 16px;
    border-radius:16px;
    border:1px solid rgba(255,255,255,.18);
    background:rgba(255,255,255,.08);
    color:white;
    font-size:1rem;
    outline:none;
  }
  input[type="text"]::placeholder{color:#dbe7ff}

  button{
    border:none;
    border-radius:16px;
    padding:14px 22px;
    font-weight:800;
    cursor:pointer;
    transition:.2s ease;
    font-size:1rem;
  }
  button:hover{transform:translateY(-1px) scale(1.02)}
  .btn-main{
    background:linear-gradient(90deg,var(--light),var(--lav),var(--pink));
    color:#081b4b;
  }
  .btn-alt{
    background:rgba(255,255,255,.08);
    color:white;
    border:1px solid rgba(255,255,255,.12);
  }

  .topbar{
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:12px;
    flex-wrap:wrap;
    margin-bottom:12px;
  }
  .stage-title{
    font-size:1.6rem;
    font-weight:800;
  }
  .meta{
    color:#d6e4ff;
    font-size:.96rem;
  }

  .progress{
    width:100%;
    height:16px;
    background:rgba(255,255,255,.08);
    border-radius:999px;
    overflow:hidden;
    border:1px solid rgba(255,255,255,.08);
    margin:8px 0 18px;
  }
  .bar{
    height:100%;
    width:0%;
    background:linear-gradient(90deg,var(--light),var(--lav),var(--pink));
    transition:width .35s ease;
  }

  .text-panel{
    background:rgba(255,255,255,.05);
    border:1px solid rgba(255,255,255,.10);
    border-radius:22px;
    padding:22px;
    white-space:pre-wrap;
    line-height:1.8;
    color:#f9fbff;
    max-height:470px;
    overflow:auto;
    user-select:text;
  }

  .question{
    margin-top:18px;
    background:rgba(255,255,255,.045);
    border:1px solid rgba(255,255,255,.1);
    border-radius:20px;
    padding:18px;
  }
  .q-head{
    display:flex;
    justify-content:space-between;
    gap:10px;
    flex-wrap:wrap;
    margin-bottom:10px;
  }
  .q-num{
    color:var(--pink);
    font-weight:800;
  }
  .q-std{
    color:var(--light);
    font-weight:700;
    font-size:.95rem;
  }
  .q-text{
    line-height:1.7;
    margin-bottom:10px;
  }

  .option{
    display:block;
    margin:10px 0;
    padding:12px 14px;
    border-radius:14px;
    background:rgba(255,255,255,.05);
    border:1px solid rgba(255,255,255,.06);
    cursor:pointer;
  }
  .option:hover{background:rgba(255,255,255,.085)}
  .option input{margin-right:8px;transform:translateY(1px)}
  .choose-note{
    color:#ffe8f7;
    font-size:.92rem;
    margin:6px 0 10px;
    font-style:italic;
  }

  .fill-blank{
    display:inline-block;
    min-width:220px;
    padding:10px 12px;
    border-radius:12px;
    background:rgba(255,255,255,.1);
    border:1px solid rgba(255,255,255,.14);
    color:white;
    outline:none;
  }

  .drag-bank,.drop-wrap{
    display:flex;
    flex-wrap:wrap;
    gap:12px;
    margin-top:12px;
  }
  .drag-item{
    padding:10px 14px;
    border-radius:14px;
    background:linear-gradient(90deg,var(--light),var(--lav));
    color:#071948;
    font-weight:800;
    cursor:grab;
    user-select:none;
  }
  .drop-zone{
    flex:1 1 280px;
    min-height:120px;
    border:2px dashed rgba(255,255,255,.24);
    border-radius:18px;
    padding:14px;
    background:rgba(255,255,255,.04);
  }
  .drop-zone h4{
    margin:0 0 10px;
    color:var(--gold);
  }

  .nav{
    display:flex;
    justify-content:space-between;
    gap:10px;
    flex-wrap:wrap;
    margin-top:20px;
  }

  .results h2{
    margin-top:0;
    font-size:2.4rem;
    color:var(--light);
  }
  .score{
    font-size:1.3rem;
    margin:8px 0 16px;
  }
  .summary-box{
    background:rgba(255,255,255,.05);
    border:1px solid rgba(255,255,255,.08);
    border-radius:18px;
    padding:16px;
    margin-top:14px;
    text-align:left;
  }
  .summary-box h3{
    margin:0 0 10px;
    color:var(--pink);
  }

  .certificate{
    margin-top:22px;
    position:relative;
    overflow:hidden;
    background:
      radial-gradient(circle at top left, rgba(255,154,213,.28), transparent 24%),
      radial-gradient(circle at bottom right, rgba(127,211,255,.28), transparent 24%),
      linear-gradient(135deg,#fffdfd,#f7f1ff,#eef8ff);
    color:#10225e;
    border:10px double #d899ff;
    border-radius:28px;
    padding:34px;
    text-align:center;
    box-shadow:0 0 0 5px rgba(255,216,107,.35) inset, 0 0 24px rgba(255,255,255,.4) inset;
  }
  .certificate:before,
  .certificate:after{
    content:"✦";
    position:absolute;
    font-size:3rem;
    color:#f08cc7;
    opacity:.35;
  }
  .certificate:before{top:16px;left:22px}
  .certificate:after{bottom:16px;right:22px}
  .certificate h2{margin:0;color:#2448af}
  .certificate .big-name{
    font-size:2.1rem;
    color:#c34ca1;
    font-weight:900;
    margin:12px 0;
  }
  .mastery{
    display:inline-block;
    margin-top:14px;
    padding:10px 18px;
    border-radius:999px;
    background:linear-gradient(90deg,var(--gold),#fff1a8);
    color:#7a4b00;
    font-weight:900;
    letter-spacing:.5px;
  }

  .credit{
    margin-top:14px;
    text-align:center;
    color:#d5dfff;
    font-size:.88rem;
  }

  @media print{
    body{background:white}
    .sparkle-layer,.nav,#startScreen,.progress,.credit,.result-actions{display:none !important}
    .card{box-shadow:none;border:1px solid #ddd;background:white;color:#111}
    .certificate{display:block !important}
  }
</style>
</head>
<body>
<div class="sparkle-layer" id="sparkles"></div>

<div class="wrap">
  <div id="startScreen" class="card center">
    <h1>LOCK IN</h1>
    <div class="sub">7th Grade Reading Practice</div>
    <div class="quote">“You can’t use up creativity. The more you use, the more you have.”</div>
    <div class="quote-author">— Maya Angelou</div>

    <div class="inputRow">
      <input id="studentName" type="text" placeholder="Enter your full name" autocomplete="off" />
      <button class="btn-main" onclick="startGame()">Start</button>
    </div>
  </div>

  <div id="gameScreen" class="card hidden">
    <div class="topbar">
      <div>
        <div class="stage-title" id="sectionTitle">Section</div>
        <div class="meta" id="sectionMeta">Text 1 of 3</div>
      </div>
      <div class="meta" id="questionCount">8 Questions</div>
    </div>

    <div class="progress"><div class="bar" id="bar"></div></div>

    <div class="text-panel" id="textPanel"></div>
    <div id="questionsPanel"></div>

    <div class="nav">
      <button class="btn-alt" onclick="prevSection()">Back</button>
      <button class="btn-main" onclick="nextSection()">Continue</button>
    </div>

    <div class="credit">Created by DWRM. M.Ed</div>
  </div>

  <div id="resultScreen" class="card results hidden">
    <h2>Lock In Complete</h2>
    <div class="score" id="scoreText"></div>

    <div class="summary-box">
      <h3>Standards to Reteach</h3>
      <ul id="reteachList"></ul>
    </div>

    <div class="certificate hidden" id="certificate">
      <h2>Certificate of Mastery</h2>
      <p>This certifies that</p>
      <div class="big-name" id="certName"></div>
      <p>successfully completed</p>
      <h2>LOCK IN</h2>
      <p>and demonstrated strong reading analysis across literary and informational texts.</p>
      <div class="mastery" id="masteryBadge">MASTERED • 75%+</div>
    </div>

    <div class="result-actions" style="margin-top:16px;">
      <button class="btn-main hidden" id="printBtn" onclick="window.print()">Print Certificate</button>
      <button class="btn-alt" onclick="location.reload()">Restart</button>
    </div>
  </div>
</div>

<script>
const sparkleLayer = document.getElementById("sparkles");
for(let i=0;i<95;i++){
  const s=document.createElement("div");
  s.className="sparkle"+(Math.random()>.78?" big":"");
  s.style.left=Math.random()*100+"%";
  s.style.top=Math.random()*100+"%";
  s.style.animationDelay=(Math.random()*4)+"s";
  s.style.animationDuration=(3+Math.random()*4)+"s";
  sparkleLayer.appendChild(s);
}

document.addEventListener("copy", e => e.preventDefault());
document.addEventListener("cut", e => e.preventDefault());
document.addEventListener("paste", e => e.preventDefault());
document.addEventListener("contextmenu", e => e.preventDefault());
document.addEventListener("keydown", function(e){
  const k = e.key.toLowerCase();
  if((e.ctrlKey || e.metaKey) && ["c","x","v","u","s","a","p"].includes(k)){
    e.preventDefault();
  }
});

const infoText = `# The Weighing of the Heart

In ancient Egypt, people believed that life did not end when a person died. Instead, they believed that every person began a journey into the afterlife. The Egyptians thought that the choices people made while they were alive would decide what happened to them after death. One of the most important parts of this journey was called the Weighing of the Heart. This ceremony was believed to determine whether a person was worthy to enter the peaceful afterlife.

The Weighing of the Heart took place in the Hall of Two Truths. According to Egyptian beliefs, the dead person was led into this hall by Anubis, the god of mummification and the dead. Anubis was usually shown with the body of a man and the head of a jackal. He guided the soul safely to the ceremony and carefully watched over the weighing process.

At the center of the hall stood a large scale. On one side of the scale, Anubis placed the person's heart. The ancient Egyptians believed the heart was the center of a person's thoughts, feelings, and actions. Unlike many people today, they did not believe the brain controlled a person's behavior. They believed the heart held every memory, every choice, and every truth about a person's life.

On the other side of the scale was the feather of Ma'at. Ma'at was the goddess of truth, justice, balance, and order. Her feather represented honesty and goodness. The Egyptians believed that people should try to live according to the rules of Ma'at by being fair, truthful, respectful, and kind. If a person followed these values during life, the heart would be light enough to balance with the feather.

As the weighing began, the god Thoth stood nearby to record the result. Thoth was the god of wisdom and writing. He carefully wrote down whether the heart balanced with the feather or not. The Egyptians believed that the gods judged every person fairly. No one could hide their wrong choices or pretend to be better than they really were because the heart revealed the truth.

If the person's heart weighed the same as the feather of Ma'at, the person had passed the test. This meant the person had lived a good and moral life. The soul was then allowed to continue into the afterlife, a peaceful place sometimes called the Field of Reeds. The Egyptians imagined the Field of Reeds as a perfect land filled with happiness, food, family, and safety.

However, if the heart was heavier than the feather, it meant the person had committed too many wrong actions during life. A heavy heart showed that the person had been dishonest, cruel, selfish, or unfair. If this happened, the soul could not enter the afterlife. Instead, the heart was thrown to Ammit, a terrifying creature with the head of a crocodile, the body of a lion, and the back legs of a hippopotamus.

Ammit was known as the "Devourer of the Dead." Once she ate the person's heart, the soul was destroyed forever. This punishment was considered far worse than death because the person would never be able to live again in the afterlife. The Egyptians used this belief to teach people that their actions mattered. They believed that every decision had consequences and that people should try to live honestly and responsibly.

The Weighing of the Heart shows that the ancient Egyptians cared deeply about justice and morality. They believed that a person's true character was more important than wealth, power, or fame. Through this story, the Egyptians taught that people should treat others fairly and make good choices. Even today, the idea of the Weighing of the Heart reminds people that honesty, kindness, and justice are important values that can shape a person's life.`;

const poemText = `The sea rose up with roaring might,
And swallowed ships into the night.
The sailor clung to broken wood,
And prayed as long as one man could.

The storm was fierce, the waves were high,
Like angry hands beneath the sky.
His ship was lost, his crew was gone,
Yet still he drifted, holding on.

At last he reached a lonely shore,
Of shining sand and nothing more.
Tall palms bent low beside the sea,
Yet not a soul did he there see.

He wandered weak through tangled trees,
And listened to the whispering breeze.
Then suddenly the earth did shake,
As though the island split and quaked.

A serpent rose from shadows deep,
Its golden eyes did never sleep.
Its scales were bright as emerald flame,
And terror seized the sailor’s frame.

Its body curled from sand to sky,
So vast it seemed to touch the high.
Yet when it spoke, its voice was slow,
As gentle as a river’s flow.

“Why do you tremble, child of sea?
No evil have I planned for thee.
The storm has cast you to this land,
Not by your will, but fate’s own hand.”

The sailor bowed his weary head,
For fear and wonder filled instead.
“I lost my friends, my ship, my way.
I thought that I would die today.”

The serpent sighed a mournful sound,
Like wind that circles all around.
“I too have known great loss and pain;
I once had kin upon this plain.

But fire came down from heaven bright,
And took them from me in one night.
Alone I stayed, yet still I live.
The heart must heal, the soul forgive.”

The sailor listened through his tears,
And slowly lost his dreadful fears.
The serpent taught him to endure,
That fate is harsh, but hope is sure.

“For every storm that breaks the sea,
A calmer shore there yet may be.
Though sorrow leaves its heavy scar,
Your strength is greater than you are.”

Three days the sailor stayed and learned,
While bright stars overhead still burned.
Then one fair dawn a ship appeared,
The very thing he thought not near.

The serpent smiled and raised its head.
“Go now,” the mighty creature said.
“Remember what the storm has shown:
Though fate may bend you, stand your own.”

The sailor sailed across the foam,
And at long last returned back home.
Yet in his heart there always stayed
The serpent’s words that never fade.`;

const storyText = `Each evening, as the golden light of day began to fade, the great sun god Ra stood at the edge of the western horizon. The people below saw only a sunset, but Ra knew it was the beginning of his most dangerous journey. He was not just the bringer of light—he was its protector. And every night, that light was threatened.

Ra stepped onto his solar boat, the sacred vessel that would carry him through the Duat, the underworld. Though he was powerful, Ra was not careless. Age had touched him. His strength was not as boundless as it once was, and the journey had grown harder with each passing night. Still, he carried a quiet determination. If he did not travel through the darkness, the sun would never rise again.

The boat pushed forward into the shadows, and the Duat came alive around him. Strange creatures whispered in the dark, and spirits watched silently as Ra passed. Some bowed in respect, while others hid in fear. Ra was not alone—gods and guardians traveled with him—but even among them, there was tension. They all knew what waited ahead.

Deep within the underworld lurked Apophis, a massive serpent of chaos who hated light and order. Apophis did not rest. He waited. Every night, he gathered his strength, preparing to strike at the one being who kept the world in balance—Ra.

As the hours passed, Ra grew quiet. He thought of the people above—the farmers who depended on the sun, the children who laughed in daylight, and the families who trusted that morning would come. He carried their hopes with him. This was more than a journey; it was a responsibility.

Suddenly, the waters of the Duat began to churn. The boat shook violently. A low, hissing sound echoed through the darkness. From the depths rose Apophis, his massive body coiling around the path ahead. His eyes burned with hatred, and his voice slithered through the air like poison.

“This is the night you fall,” Apophis hissed. “The world will finally belong to darkness.”

Ra stood tall, though he felt the weight of the battle ahead. “As long as I rise, light will never be defeated,” he replied. His voice was steady—not because he felt no fear, but because he refused to let fear control him.

The battle began. Waves crashed, the boat strained, and the guardians fought to hold their ground. Ra summoned all his remaining strength, calling upon the power of light itself. Though Apophis was strong, he was driven by destruction. Ra, however, was driven by purpose.

With a final surge of energy, Ra struck back. The light burst through the darkness, forcing Apophis to retreat into the depths once more. The serpent was not destroyed—he never was—but he was defeated for that night.

The Duat grew still again. Ra, exhausted but unbroken, continued his journey. Slowly, the darkness began to fade. A faint glow appeared on the horizon, growing stronger with each moment.

At last, Ra emerged into the sky once more, rising as the sun. The world below awakened—birds sang, people rose, and life continued. No one saw the battle he had fought, but they felt its result in the warmth of the morning light.

And as Ra climbed higher into the sky, he knew that when night came again, the journey would begin once more. Not because it was easy—but because it was necessary.`;

const sections = [
  {
    fullTitle:"Informational Text: The Weighing of the Heart",
    text:infoText,
    questions:[
      {
        type:"single",
        standard:"RI.7.2",
        prompt:"Which statement best expresses the central idea of the article?",
        options:[
          "Ancient Egyptians feared all of their gods equally.",
          "The Weighing of the Heart showed that Egyptians valued truth, justice, and the consequences of a person’s actions.",
          "Mummification was the most important part of Egyptian religion.",
          "The Hall of Two Truths was the most beautiful place in the afterlife."
        ],
        answer:1
      },
      {
        type:"single",
        standard:"RI.7.1",
        prompt:"Which detail best supports the idea that the heart was considered the center of a person’s character?",
        options:[
          "Anubis had the head of a jackal.",
          "The Hall of Two Truths was part of the afterlife.",
          "The Egyptians believed the heart held every memory, every choice, and every truth about a person’s life.",
          "Thoth recorded the result of the weighing."
        ],
        answer:2
      },
      {
        type:"single",
        standard:"RI.7.3",
        prompt:"How does the section about the feather of Ma'at help develop the ideas in the article?",
        options:[
          "It explains why the scale was made of gold.",
          "It shows what values the Egyptians believed people should live by.",
          "It proves that the gods often disagreed with each other.",
          "It describes how the dead person entered the hall."
        ],
        answer:1
      },
      {
        type:"multi",
        standard:"RI.7.8",
        prompt:"Which TWO details best support the claim that the Egyptians believed actions had consequences after death?",
        options:[
          "If the heart balanced with the feather, the soul could enter the afterlife.",
          "Anubis guided the dead person to the Hall of Two Truths.",
          "If the heart was heavy, it was thrown to Ammit.",
          "Thoth was the god of wisdom and writing."
        ],
        answer:[0,2]
      },
      {
        type:"single",
        standard:"RI.7.4",
        prompt:"What does the word “worthy” most nearly mean as it is used in the first paragraph?",
        options:[
          "ready to leave quickly",
          "deserving to be accepted",
          "afraid of punishment",
          "eager to meet the gods"
        ],
        answer:1
      },
      {
        type:"single",
        standard:"RI.7.6",
        prompt:"How does the author mainly present information in this article?",
        options:[
          "by giving a biased opinion against Egyptian beliefs",
          "by explaining the ceremony step by step in a clear, respectful way",
          "by comparing Egyptian gods to modern leaders",
          "by arguing that the afterlife was not real"
        ],
        answer:1
      },
      {
        type:"drag",
        standard:"RI.7.3 / RI.7.8",
        prompt:"Drag each detail into the category it best supports.",
        items:[
          {text:"The heart held every memory, choice, and truth.", target:"Beliefs about character"},
          {text:"The heart was thrown to Ammit if it was too heavy.", target:"Consequences after death"},
          {text:"The soul could enter the Field of Reeds if the heart balanced with the feather.", target:"Consequences after death"},
          {text:"The Egyptians believed the heart, not the brain, controlled behavior.", target:"Beliefs about character"}
        ],
        zones:["Beliefs about character","Consequences after death"]
      },
      {
        type:"multi",
        standard:"RI.7.2 / RI.7.8",
        prompt:"Which TWO ideas are best supported by the article’s ending?",
        options:[
          "The Egyptians believed true character mattered more than wealth or power.",
          "The Egyptians used the Weighing of the Heart to teach moral lessons about honesty and fairness.",
          "Only kings were expected to live according to Ma'at.",
          "Most Egyptians believed fame guaranteed a peaceful afterlife."
        ],
        answer:[0,1]
      }
    ]
  },
  {
    fullTitle:"Poem: The Tale of the Shipwrecked Sailor",
    text:poemText,
    questions:[
      {
        type:"single",
        standard:"RL.7.2",
        prompt:"Which statement best expresses a theme of the poem?",
        options:[
          "People should avoid the sea whenever possible.",
          "Hope and inner strength can help people survive even after great loss.",
          "Creatures that seem frightening are always dangerous.",
          "It is impossible to recover after sorrow."
        ],
        answer:1
      },
      {
        type:"single",
        standard:"RL.7.1",
        prompt:"Which detail best supports the idea that the sailor refuses to give up?",
        options:[
          "“Tall palms bent low beside the sea”",
          "“Its scales were bright as emerald flame”",
          "“Yet still he drifted, holding on”",
          "“The sailor bowed his weary head”"
        ],
        answer:2
      },
      {
        type:"single",
        standard:"RL.7.4",
        prompt:"What is the effect of comparing the waves to “angry hands beneath the sky”?",
        options:[
          "It makes the storm seem playful and exciting.",
          "It helps the reader imagine the storm as violent and threatening.",
          "It shows that the sailor enjoys the danger.",
          "It suggests the sea is calm and gentle."
        ],
        answer:1
      },
      {
        type:"single",
        standard:"RL.7.3",
        prompt:"How does the serpent’s character change the direction of the poem?",
        options:[
          "The serpent increases the sailor’s fear and makes him want to flee.",
          "The serpent changes the poem from one of terror alone to one of comfort, wisdom, and healing.",
          "The serpent causes the sailor to become angry and reckless.",
          "The serpent turns the poem into a humorous adventure."
        ],
        answer:1
      },
      {
        type:"multi",
        standard:"RL.7.1 / RL.7.3",
        prompt:"Which TWO details best show that the serpent is wise rather than evil?",
        options:[
          "It tells the sailor, “No evil have I planned for thee.”",
          "Its golden eyes “did never sleep.”",
          "It shares its own story of pain and survival.",
          "Its body seems to touch the sky."
        ],
        answer:[0,2]
      },
      {
        type:"single",
        standard:"RL.7.5",
        prompt:"How does the shift from storm to calm ending contribute to the poem’s meaning?",
        options:[
          "It shows that the sailor forgot everything that happened.",
          "It emphasizes that suffering can lead to growth, wisdom, and hope.",
          "It proves that the serpent controlled the weather the whole time.",
          "It suggests the storm never truly happened."
        ],
        answer:1
      },
      {
        type:"drag",
        standard:"RL.7.4 / RL.7.5",
        prompt:"Drag each quotation into the effect it best creates in the poem.",
        items:[
          {text:"“Like angry hands beneath the sky”", target:"Creates danger and violence"},
          {text:"“As gentle as a river’s flow”", target:"Creates calm and comfort"},
          {text:"“Like wind that circles all around”", target:"Creates sadness and reflection"},
          {text:"“A calmer shore there yet may be”", target:"Creates hope and reassurance"}
        ],
        zones:["Creates danger and violence","Creates calm and comfort","Creates sadness and reflection","Creates hope and reassurance"]
      },
      {
        type:"multi",
        standard:"RL.7.2 / RL.7.5",
        prompt:"Which TWO ideas are developed by the ending of the poem?",
        options:[
          "The sailor returns home changed by what he has learned.",
          "The storm mattered only because it led to treasure.",
          "Pain can leave lasting marks, but wisdom can remain with a person.",
          "The serpent’s advice is quickly forgotten once the sailor leaves."
        ],
        answer:[0,2]
      }
    ]
  },
  {
    fullTitle:"Story: The Journey of Ra Through the Underworld",
    text:storyText,
    questions:[
      {
        type:"single",
        standard:"RL.7.2",
        prompt:"Which statement best expresses a central idea of the story?",
        options:[
          "Ra travels at night because he enjoys danger.",
          "Ra’s nightly journey shows that protecting others often requires courage, sacrifice, and perseverance.",
          "Apophis defeats Ra almost every night.",
          "The people below fully understand Ra’s struggles."
        ],
        answer:1
      },
      {
        type:"single",
        standard:"RL.7.1",
        prompt:"Which detail best supports the idea that Ra’s journey is a duty, not a choice for pleasure?",
        options:[
          "“The people below saw only a sunset”",
          "“If he did not travel through the darkness, the sun would never rise again.”",
          "“Some bowed in respect, while others hid in fear.”",
          "“A faint glow appeared on the horizon”"
        ],
        answer:1
      },
      {
        type:"single",
        standard:"RL.7.3",
        prompt:"How does the introduction of Apophis affect the plot?",
        options:[
          "It creates the main conflict by giving Ra a powerful enemy who threatens light and order.",
          "It solves the problem of the journey too early.",
          "It makes Ra seem less responsible for the world.",
          "It turns the story into a mystery about the underworld."
        ],
        answer:0
      },
      {
        type:"single",
        standard:"RL.7.4",
        prompt:"What is the effect of describing Apophis’s voice as slithering “through the air like poison”?",
        options:[
          "It makes Apophis seem weak and harmless.",
          "It helps the reader picture Apophis as dangerous and filled with evil intent.",
          "It suggests Apophis is trying to help Ra.",
          "It shows the underworld is peaceful."
        ],
        answer:1
      },
      {
        type:"multi",
        standard:"RL.7.1 / RL.7.6",
        prompt:"Which TWO details best reveal Ra’s character as determined and responsible?",
        options:[
          "He thinks about the farmers, children, and families who depend on the sun.",
          "He admits that he is stronger than ever before.",
          "He continues the journey even though it has become harder with age.",
          "He asks the spirits of the Duat to fight without him."
        ],
        answer:[0,2]
      },
      {
        type:"single",
        standard:"RL.7.5",
        prompt:"Why is the battle with Apophis placed near the end of the story rather than at the beginning?",
        options:[
          "It allows suspense to build as readers understand what Ra is risking before the conflict reaches its peak.",
          "It prevents readers from learning anything about the underworld.",
          "It proves that Apophis is not important to the story.",
          "It makes the story mostly about the people below."
        ],
        answer:0
      },
      {
        type:"single",
        standard:"RL.7.6",
        prompt:"How does the narrator mainly present Ra?",
        options:[
          "as careless and overconfident",
          "as powerful but also burdened by responsibility",
          "as fearful and unwilling to fight",
          "as mysterious and impossible to understand"
        ],
        answer:1
      },
      {
        type:"drag",
        standard:"RL.7.3 / RL.7.5",
        prompt:"Drag each event into the role it plays in the story.",
        items:[
          {text:"Ra enters the Duat on his solar boat.", target:"Beginning / setup"},
          {text:"Apophis rises and attacks the boat.", target:"Rising action / conflict"},
          {text:"Ra defeats Apophis for the night.", target:"Climax"},
          {text:"Ra rises again as the sun.", target:"Resolution"}
        ],
        zones:["Beginning / setup","Rising action / conflict","Climax","Resolution"]
      }
    ]
  }
];

let currentSection = 0;
let playerName = "";
let answers = {};

function esc(str){
  return String(str).replace(/[&<>"']/g, m => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[m]));
}
function shuffle(arr){
  const copy=[...arr];
  for(let i=copy.length-1;i>0;i--){
    const j=Math.floor(Math.random()*(i+1));
    [copy[i],copy[j]]=[copy[j],copy[i]];
  }
  return copy;
}
function arraysEqual(a,b){
  if(!Array.isArray(a) || !Array.isArray(b) || a.length!==b.length) return false;
  const aa=[...a].sort((x,y)=>x-y);
  const bb=[...b].sort((x,y)=>x-y);
  return aa.every((v,i)=>v===bb[i]);
}
function normalize(text){
  return String(text).trim().toLowerCase().replace(/[“”"'.!,?]/g,"");
}
function gradeDrag(q, response){
  if(!response) return false;
  return q.items.every(item => {
    const placed = response[item.target] || [];
    return placed.includes(item.text);
  });
}
function scrollTopNow(){
  window.scrollTo({top:0, behavior:"smooth"});
}

function prepareQuestions(){
  sections.forEach(sec=>{
    sec.questions.forEach(q=>{
      if((q.type==="single" || q.type==="multi") && !q._prepared){
        const items=q.options.map((t,i)=>({t,i}));
        const s=shuffle(items);
        q.options=s.map(x=>x.t);
        if(q.type==="single"){
          q.answer=s.findIndex(x=>x.i===q.answer);
        }else{
          q.answer=s.map((x,newIndex)=>q.answer.includes(x.i) ? newIndex : null).filter(v=>v!==null);
        }
        q._prepared=true;
      }
      if(q.type==="drag" && !q._prepared){
        q.items=shuffle(q.items);
        q._prepared=true;
      }
    });
  });
}

function startGame(){
  const name = document.getElementById("studentName").value.trim();
  if(!name){
    alert("Please enter your name.");
    return;
  }
  playerName = name;
  prepareQuestions();
  document.getElementById("startScreen").classList.add("hidden");
  document.getElementById("gameScreen").classList.remove("hidden");
  renderSection();
  scrollTopNow();
}

function renderSection(){
  const sec = sections[currentSection];
  document.getElementById("sectionTitle").textContent = sec.fullTitle;
  document.getElementById("sectionMeta").textContent = `Text ${currentSection+1} of ${sections.length}`;
  document.getElementById("questionCount").textContent = `${sec.questions.length} Questions`;
  document.getElementById("bar").style.width = (((currentSection+1)/sections.length)*100) + "%";
  document.getElementById("textPanel").textContent = sec.text;
  renderQuestions(sec);
  scrollTopNow();
}

function renderQuestions(sec){
  const panel = document.getElementById("questionsPanel");
  panel.innerHTML = "";

  sec.questions.forEach((q, i)=>{
    const key = `${currentSection}_${i}`;
    const saved = answers[key];
    const div = document.createElement("div");
    div.className = "question";

    let html = `
      <div class="q-head">
        <div class="q-num">Question ${i+1}</div>
        <div class="q-std">${esc(q.standard)}</div>
      </div>
      <div class="q-text">${esc(q.prompt)}</div>
    `;

    if(q.type === "single"){
      q.options.forEach((opt, idx)=>{
        const checked = saved === idx ? "checked" : "";
        html += `
          <label class="option">
            <input type="radio" name="q_${currentSection}_${i}" value="${idx}" ${checked}>
            ${esc(opt)}
          </label>
        `;
      });
    }

    if(q.type === "multi"){
      html += `<div class="choose-note">Choose two answers.</div>`;
      q.options.forEach((opt, idx)=>{
        const checked = Array.isArray(saved) && saved.includes(idx) ? "checked" : "";
        html += `
          <label class="option">
            <input type="checkbox" name="q_${currentSection}_${i}" value="${idx}" ${checked}>
            ${esc(opt)}
          </label>
        `;
      });
    }

    if(q.type === "fill"){
      html += `<input class="fill-blank" type="text" id="fill_${currentSection}_${i}" value="${saved ? esc(saved) : ""}" autocomplete="off" />`;
    }

    if(q.type === "drag"){
      html += `<div class="drag-bank" id="bank_${currentSection}_${i}"></div>`;
      html += `<div class="drop-wrap">`;
      q.zones.forEach((z, zi)=>{
        html += `<div class="drop-zone" id="zone_${currentSection}_${i}_${zi}" data-zone="${esc(z)}"><h4>${esc(z)}</h4></div>`;
      });
      html += `</div>`;
    }

    div.innerHTML = html;
    panel.appendChild(div);

    if(q.type === "drag"){
      setupDragQuestion(q, i, saved);
    }
  });
}

function setupDragQuestion(q, questionIndex, saved){
  const bank = document.getElementById(`bank_${currentSection}_${questionIndex}`);
  const placements = saved || {};
  const placedTexts = new Set();

  q.zones.forEach(zone=>{
    if(placements[zone]){
      placements[zone].forEach(t=>placedTexts.add(t));
    }
  });

  q.items.forEach((item, idx)=>{
    const el = document.createElement("div");
    el.className = "drag-item";
    el.textContent = item.text;
    el.draggable = true;
    el.id = `drag_${currentSection}_${questionIndex}_${idx}`;
    el.dataset.label = item.text;
    el.dataset.target = item.target;

    el.addEventListener("dragstart", e=>{
      e.dataTransfer.setData("text/plain", el.id);
    });

    let placed = false;
    q.zones.forEach((zone, zi)=>{
      if(placements[zone] && placements[zone].includes(item.text)){
        document.getElementById(`zone_${currentSection}_${questionIndex}_${zi}`).appendChild(el);
        placed = true;
      }
    });

    if(!placed && !placedTexts.has(item.text)){
      bank.appendChild(el);
    }
  });

  q.zones.forEach((zone, zi)=>{
    const z = document.getElementById(`zone_${currentSection}_${questionIndex}_${zi}`);
    z.addEventListener("dragover", e=>e.preventDefault());
    z.addEventListener("drop", e=>{
      e.preventDefault();
      const id = e.dataTransfer.getData("text/plain");
      const dragged = document.getElementById(id);
      if(dragged) z.appendChild(dragged);
    });
  });

  bank.addEventListener("dragover", e=>e.preventDefault());
  bank.addEventListener("drop", e=>{
    e.preventDefault();
    const id = e.dataTransfer.getData("text/plain");
    const dragged = document.getElementById(id);
    if(dragged) bank.appendChild(dragged);
  });
}

function saveCurrentSection(){
  const sec = sections[currentSection];
  sec.questions.forEach((q,i)=>{
    const key = `${currentSection}_${i}`;

    if(q.type==="single"){
      const checked = document.querySelector(`input[name="q_${currentSection}_${i}"]:checked`);
      answers[key] = checked ? Number(checked.value) : null;
    }

    if(q.type==="multi"){
      const checked = Array.from(document.querySelectorAll(`input[name="q_${currentSection}_${i}"]:checked`)).map(x=>Number(x.value));
      answers[key] = checked;
    }

    if(q.type==="fill"){
      const v = document.getElementById(`fill_${currentSection}_${i}`);
      answers[key] = v ? v.value.trim() : "";
    }

    if(q.type==="drag"){
      const result = {};
      q.zones.forEach((zone, zi)=>{
        const zoneEl = document.getElementById(`zone_${currentSection}_${i}_${zi}`);
        result[zone] = Array.from(zoneEl.querySelectorAll(".drag-item")).map(x=>x.dataset.label);
      });
      answers[key] = result;
    }
  });
}

function prevSection(){
  saveCurrentSection();
  if(currentSection>0){
    currentSection--;
    renderSection();
  }
}

function nextSection(){
  saveCurrentSection();
  if(currentSection < sections.length-1){
    currentSection++;
    renderSection();
  } else {
    showResults();
  }
}

function showResults(){
  document.getElementById("gameScreen").classList.add("hidden");
  document.getElementById("resultScreen").classList.remove("hidden");

  let total = 0;
  let correct = 0;
  const misses = {};

  sections.forEach((sec, si)=>{
    sec.questions.forEach((q, qi)=>{
      total++;
      const key = `${si}_${qi}`;
      const resp = answers[key];
      let ok = false;

      if(q.type==="single"){
        ok = Number(resp) === q.answer;
      } else if(q.type==="multi"){
        ok = arraysEqual(resp, q.answer);
      } else if(q.type==="fill"){
        ok = normalize(resp) === normalize(q.answer);
      } else if(q.type==="drag"){
        ok = gradeDrag(q, resp);
      }

      if(ok){
        correct++;
      } else {
        misses[q.standard] = (misses[q.standard] || 0) + 1;
      }
    });
  });

  const percent = Math.round((correct / total) * 100);
  document.getElementById("scoreText").textContent =
    `${playerName} scored ${correct} out of ${total} — ${percent}%.`;

  const reteach = document.getElementById("reteachList");
  reteach.innerHTML = "";
  const missEntries = Object.entries(misses).sort((a,b)=>b[1]-a[1]);

  if(missEntries.length === 0){
    reteach.innerHTML = "<li>None — excellent work across all standards.</li>";
  } else {
    missEntries.forEach(([std,count])=>{
      const li = document.createElement("li");
      li.textContent = `${std} — ${count} question(s) missed`;
      reteach.appendChild(li);
    });
  }

  const cert = document.getElementById("certificate");
  const printBtn = document.getElementById("printBtn");

  if(percent >= 75){
    cert.classList.remove("hidden");
    printBtn.classList.remove("hidden");
    document.getElementById("certName").textContent = playerName;
    document.getElementById("masteryBadge").textContent = `MASTERED • ${percent}%`;
  } else {
    cert.classList.add("hidden");
    printBtn.classList.add("hidden");
  }

  scrollTopNow();
}
</script>
</body>
</html>
