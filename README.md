<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>Ankit — Will you be my Valentine? ❤️</title>
<style>
  :root{
    --bg1:#ff9aa2;
    --bg2:#ffb7b2;
    --accent:#ff4d6d;
    --white:#fff;
    --card:#fff6f8;
    --shadow: 0 20px 50px rgba(0,0,0,0.18);
  }

  /* Page */
  html,body{height:100%;margin:0;font-family: "Georgia", "Palatino", serif;background:linear-gradient(135deg,var(--bg1),var(--bg2));-webkit-font-smoothing:antialiased;display:flex;align-items:center;justify-content:center;color:#333;}
  .stage{width:95%;max-width:820px;padding:30px;box-sizing:border-box;position:relative;display:flex;align-items:center;justify-content:center;flex-direction:column;}

  /* Bubbly background */
  .bubbles{
    position:absolute;inset:0;pointer-events:none;overflow:hidden;
  }
  .bubble{
    position:absolute;border-radius:50%;opacity:0.12;background:var(--white);
    animation:rise linear infinite;
    filter:blur(.4px);
  }
  @keyframes rise{
    0%{transform:translateY(120%) scale(.8);opacity:0;}
    10%{opacity:0.08;}
    100%{transform:translateY(-30%) scale(1.2);opacity:0;}
  }

  /* Card / Envelope container */
  .card{
    width:720px;max-width:100%;background:transparent;border-radius:18px;padding:18px;display:flex;align-items:center;justify-content:center;position:relative;
  }

  /* Envelope */
  .envelope{
    width:420px;max-width:86vw;height:260px;background:linear-gradient(180deg,#fff 0%, #ffeef2 100%);border-radius:12px;position:relative;box-shadow:var(--shadow);overflow:visible;
    transform-style:preserve-3d;
  }
  .envelope .body{
    position:absolute;inset:0;border-radius:12px;background:linear-gradient(180deg,#fff 0%, #fff6f8 100%);display:flex;align-items:center;justify-content:center;padding:28px;box-sizing:border-box;
  }

  /* Flap */
  .flap{
    position:absolute;left:50%;top:-6px;width:100%;height:140px;transform:translateX(-50%);transform-origin:50% 100%;background:linear-gradient(180deg,#ffedf1 0%, #ffd7df 100%);clip-path:polygon(0 0,100% 0,50% 100%);border-radius:8px;box-shadow:0 8px 18px rgba(0,0,0,0.12);
    transition:transform 700ms cubic-bezier(.2,.9,.2,1);
    z-index:3;
  }
  .envelope.open .flap{transform:translateX(-50%) rotateX(-180deg);}

  /* Letter inside */
  .letter{
    width:92%;height:84%;background:linear-gradient(180deg,#fff 0%, #fffdfb 100%);border-radius:8px;padding:20px;box-sizing:border-box;box-shadow:inset 0 1px 0 rgba(255,255,255,0.6);
    transform:translateY(110%);transition:transform 700ms cubic-bezier(.2,.9,.2,1);
    z-index:1;position:relative;
  }
  .envelope.open .letter{transform:translateY(0%);}

  /* Letter content */
  .greeting{font-size:26px;color:var(--accent);margin:4px 0 8px 0;text-align:center;}
  .copy{font-size:16px;line-height:1.5;color:#4a4a4a;text-align:center;}
  .copy b{color:var(--accent);font-weight:700;}

  /* Buttons row */
  .actions{margin-top:14px;display:flex;gap:16px;align-items:center;justify-content:center;position:relative;height:56px;}
  button{
    border:none;padding:12px 24px;border-radius:28px;font-size:16px;cursor:pointer;box-shadow:0 8px 18px rgba(0,0,0,0.08);transition:transform .15s ease,box-shadow .15s ease;
  }
  button:active{transform:translateY(2px);}
  #yesBtn{background:var(--accent);color:white;}
  #noBtn{background:#f3f3f3;color:#555;position:absolute;transition:left .18s ease,top .18s ease,transform .12s ease;}

  /* Little dare text */
  .dare{font-weight:700;color:#6a6a6a;margin-top:8px;text-align:center;font-size:14px;}

  /* Love reveal overlay */
  .loveReveal{
    position:fixed;inset:0;display:flex;align-items:center;justify-content:center;background:rgba(10,6,8,0.35);backdrop-filter:blur(6px);visibility:hidden;opacity:0;transition:opacity .35s,visibility .35s;z-index:40;
  }
  .loveReveal.show{visibility:visible;opacity:1;}
  .loveCard{background:linear-gradient(135deg,#fff 0,#fff8fb 100%);padding:26px;border-radius:16px;max-width:680px;text-align:center;box-shadow:0 25px 60px rgba(0,0,0*
