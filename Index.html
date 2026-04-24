<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>

/* 🔥 RESET */
html, body {
  margin: 0;
  padding: 0;
  background: #0f0000; /* match member count box */
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  color: #fff;
  overflow: hidden; /* remove default scrollbar */
}

/* 🔥 WRAP */
#wrap {
  box-sizing: border-box;
  padding: 12px;

  background: #0f0000; /* match member count box */
  box-shadow: 0 0 40px #ff3c00;
  border-radius: 0;

  max-height: 420px; /* internal scroll if needed */
  overflow-y: auto;
}

/* 🔥 INFERNO SCROLLBAR */
#wrap::-webkit-scrollbar {
  width: 6px;
}

#wrap::-webkit-scrollbar-track {
  background: transparent;
}

#wrap::-webkit-scrollbar-thumb {
  background: linear-gradient(#ffae00, #ff3c00);
  box-shadow: 0 0 8px #ff3c00;
  border-radius: 10px;
}

/* Firefox */
#wrap {
  scrollbar-width: thin;
  scrollbar-color: #ff3c00 transparent;
}

/* 🔥 MEMBER LIST */
#latest-members {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

/* 🔥 MEMBER CARD */
.member {
  display: flex;
  align-items: center;
  gap: 10px;

  padding: 10px;
  border-radius: 0;

  background: linear-gradient(145deg, #140000, #1a0000);
  border: 1px solid rgba(255,60,0,0.25);

  color: #fff;
  font-size: 12px;
  text-decoration: none;
  position: relative;

  transition: all 0.2s ease;
}

/* 🔥 HOVER EFFECT */
.member:hover {
  transform: translateY(-2px);
  background: linear-gradient(145deg, #1a0000, #220000);
  border: 1px solid rgba(255,120,0,0.7);
  box-shadow:
    0 0 12px rgba(255,60,0,0.7),
    0 0 25px rgba(255,120,0,0.5);
}

/* 🔥 AVATAR */
.member img {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  border: 2px solid #ff3c00;
  object-fit: cover;
  transition: 0.2s;
}

.member:hover img {
  box-shadow:
    0 0 10px #ff3c00,
    0 0 20px #ff6a00;
}

/* 🔥 MEMBER INFO */
.info {
  display: flex;
  flex-direction: column;
}

.name {
  font-size: 13px;
  color: #fff3d1;
}

.date {
  font-size: 10px;
  color: #ffae00;
}

/* 🔥 ONLINE STATUS DOT */
.status {
  position: absolute;
  right: 8px;
  width: 8px;
  height: 8px;
  border-radius: 50%;
}

.online {
  background: #00ff88;
  box-shadow: 0 0 6px #00ff88;
}

.offline {
  background: #666;
}

</style>
</head>

<body>

<div id="wrap">
  <div id="latest-members">Loading warriors...</div>
</div>

<script>
async function load() {
  try {
    const res = await fetch("https://api.chess.com/pub/club/group-a162138be57d83c3500191b84a4b325d/members");
    const data = await res.json();

    let members = [
      ...(data.weekly || []),
      ...(data.monthly || []),
      ...(data.all_time || [])
    ];

    // 🔥 Remove duplicates
    const map = {};
    members.forEach(m => {
      if(!map[m.username] || m.joined > map[m.username].joined){
        map[m.username] = m;
      }
    });

    members = Object.values(map)
      .sort((a,b)=>b.joined-a.joined)
      .slice(0,12); // show more members

    const full = await Promise.all(
      members.map(async m => {
        try {
          const r = await fetch(`https://api.chess.com/pub/player/${m.username}`);
          const p = await r.json();
          return {
            name: m.username,
            date: new Date(m.joined*1000).toLocaleDateString(),
            avatar: p.avatar || "https://www.chess.com/bundles/web/images/noavatar_l.84a92436.gif",
            status: p.status || "offline"
          };
        } catch {
          return {
            name: m.username,
            date: new Date(m.joined*1000).toLocaleDateString(),
            avatar: "https://www.chess.com/bundles/web/images/noavatar_l.84a92436.gif",
            status: "offline"
          };
        }
      })
    );

    document.getElementById("latest-members").innerHTML =
      full.map(m => `
        <a href="https://www.chess.com/member/${m.name}" target="_blank" class="member">
          <img src="${m.avatar}">
          <div class="info">
            <div class="name">${m.name}</div>
            <div class="date">Joined ${m.date}</div>
          </div>
          <div class="status ${m.status === "online" ? "online" : "offline"}"></div>
        </a>
      `).join("");

  } catch(e) {
    document.getElementById("latest-members").innerText = "Failed to load.";
    console.error(e);
  }
}

load();
setInterval(load, 300000);
</script>

</body>
</html>
