<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>TuNoSaBeNa</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: linear-gradient(135deg, #122f65 0%, #400461 100%);
      color: #222;
      padding: 2em;
      min-height: 100vh;
    }
    .logo-svg {
  width: 180px;
  height: 180px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.logo-svg svg {
  width: 180px;
  height: auto;
  animation: latido 2.5s ease-in-out infinite;
  filter: drop-shadow(0 0 10px rgba(255,255,255,0.5));
} 
    header {
      position: sticky;
      top: 0;
      z-index: 999;
      backdrop-filter: blur(20px) saturate(180%);
      -webkit-backdrop-filter: blur(20px) saturate(180%);
      background: rgba(255, 255, 255, 0.18);
      border: 1px solid rgba(255, 255, 255, 0.164);
      padding: 1.2em;
      border-radius: 16px;
      max-width: 900px;
      margin: 0 auto;
      box-shadow: 0 4px 25px rgba(0,0,0,0.1);
      transition: backdrop-filter 0.3s ease, background 0.3s ease;
      text-align: center;
    }
    header ul { list-style: none; padding: 0; margin-top: 1em; display: flex; gap: 1.5em; justify-content: center; } header ul li a { color: #fff; text-decoration: none; font-weight: 600; transition: opacity 0.2s ease; } header ul li a:hover { opacity: 0.7; }
    h1 {
      color: #fff;
      font-size: 2.5em;
      margin: 0;
      text-shadow: 0 2px 10px rgba(0,0,0,0.3);
    }
    section {
      padding: 4em;
      margin: 1.5em auto;
      border-radius: 12px;
      max-width: 900px;
      background: rgba(255, 255, 255, 0.233);
      backdrop-filter: blur(18px) saturate(160%);
      -webkit-backdrop-filter: blur(18px) saturate(160%);
      border: 1px solid rgba(255, 255, 255, 0.103);
      box-shadow: 0 4px 25px rgba(0,0,0,0.1);
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    section:hover {
      transform: translateY(-3px);
      box-shadow: 0 6px 30px rgba(0,0,0,0.15);
    }
    h2, h3 {
      color: #111;
    }
    .video-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1em;
    }
    .video {
      position: relative;
      cursor: pointer;
      background: rgba(255, 255, 255, 0.116);
      border-radius: 12px;
      overflow: hidden;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    .video:hover {
      transform: scale(1.03);
      box-shadow: 0 4px 20px rgba(0,0,0,0.1);
    }
    .video-title {
      padding: 0.8em;
      background: rgba(255, 255, 255, 0.3);
      text-align: center;
      font-weight: 600;
      color: #fff;
      min-height: 1.5em;
      border-bottom: 1px solid rgba(255, 255, 255, 0.2);
    }
    .video img {
      width: 100%;
      display: block;
    }
    .play-button {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      font-size: 3em;
      color: white;
      text-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
      opacity: 0.85;
      transition: transform 0.2s, opacity 0.2s;
    }
    .video:hover .play-button {
      transform: translate(-50%, -50%) scale(1.1);
      opacity: 1;
    }
    audio {
      width: 100%;
      border-radius: 8px;
      background-color: rgba(255, 255, 255, 0.171);
      backdrop-filter: blur(10px);
      -webkit-backdrop-filter: blur(10px);
      border: 1px solid rgba(255, 255, 255, 0.199);
      margin-top: 0.5em;
    }
    .playlist > div {
      margin-bottom: 1.5em;
    }
    .catalogo-card {
      text-align: center;
      padding: 2em;
      border-radius: 16px;
      background: rgba(255, 255, 255, 0.226);
      backdrop-filter: blur(20px);
      border: 1px solid rgba(255, 255, 255, 0.171);
      box-shadow: 0 4px 25px rgba(0,0,0,0.1);
    }
    .catalogo-card button {
      margin-top: 1em;
      padding: 0.8em 1.8em;
      font-size: 1.1em;
      border: none;
      border-radius: 30px;
      background: linear-gradient(90deg, #0072ff, #00c6ff);
      color: white;
      cursor: pointer;
      transition: background 0.3s ease, transform 0.2s ease;
    }
    .catalogo-card button:hover {
      background: linear-gradient(90deg, #0055cc, #00aaff);
      transform: scale(1.05);
    }
    .catalogo-card img {
      max-width: 100%;
      border-radius: 12px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.15);
      margin-top: 1em;
    }
    #chatContainer {
      margin-top: 1em;
      padding: 1em;
      background: rgba(255, 255, 255, 0.5);
      border-radius: 12px;
      min-height: 300px;
    }
    footer {
      text-align: center;
      padding: 1em;
      background: rgba(255, 255, 255, 0.164);
      border-radius: 12px;
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255, 255, 255, 0.185);
      margin-top: 2em;
      font-size: 1em;
      color: #fff;
    }
  </style>
</head>
<body>
  <header>
  <div class="logo">
    <div class="logo-svg">
<svg 
<g fill="#ece800" stroke="#000" stroke-width="5.32763" inkscape:groupmode="layer" inkscape:label="Image 1">
<path d="m40.836545 111.32457c30.356664-34.918548 91.060895-105.0796173 91.060895-105.0796173l52.10143 56.5385763h-56.22932l-33.207216 48.874471z" inkscape:export-filename="C:\Users\LURDES\Downloads\Bad Bunny\logo 1.png" inkscape:export-xdpi="278.00699" inkscape:export-ydpi="278.00699" sodipodi:nodetypes="cccccc"/>
<path d="m162.9914 93.546757 46.40032-0.05171 45.99317 52.432783-49.30615-0.31743z" inkscape:export-filename="C:\Users\LURDES\Downloads\Bad Bunny\logo 1.png" inkscape:export-xdpi="278.00699" inkscape:export-ydpi="278.00699" sodipodi:nodetypes="ccccc"/>
<path d="m115.01787 88.149916 15.46311-21.438009 165.52884-0.149319c13.31594-0.121186 21.23502 9.149847 18.6887 16.648535l-14.76252 42.875457c-2.48126 7.29965-11.49644 15.04008-19.39546 15.04008h-20.93901l-22.48481-23.79477c10.6501-0.13809 14.99161 0.15922 23.16692-0.29021 5.92596-1.43038 6.20223-5.60989 7.53832-10.55052l2.90307-18.117038z" inkscape:export-filename="C:\Users\LURDES\Downloads\Bad Bunny\logo 1.png" inkscape:export-xdpi="278.00699" inkscape:export-ydpi="278.00699" sodipodi:nodetypes="cccccccccccc"/>
<path d="m190.94455 62.783527 3.45507-29.855695c0.67628-5.231108 1.43739-15.53529 22.6149-16.386958h113.38884l-3.14098 16.386958c-0.73151 4.460991-8.12482 7.223938-13.19203 6.958847l-72.87036-0.448956c-6.20698-0.378845-9.708 1.833534-10.3652 6.060929l-0.94232 8.530199 16.96121 8.754678z" inkscape:export-filename="C:\Users\LURDES\Downloads\Bad Bunny\logo 1.png" inkscape:export-xdpi="278.00699" inkscape:export-ydpi="278.00699" sodipodi:nodetypes="ccccccccccc"/>
<path d="m38.293703 115.76054 133.490967 0.22449 20.25922 25.14163h-177.164808z" inkscape:export-filename="C:\Users\LURDES\Downloads\Bad Bunny\logo 1.png" inkscape:export-xdpi="278.00699" inkscape:export-ydpi="278.00699" sodipodi:nodetypes="ccccc"/>
</g>
<g inkscape:groupmode="layer" inkscape:label="Image 2">
<text transform="scale(1.1828883 .84538835)" x="5.8197217" y="215.26418" fill="#ece800" font-family="Impact" font-size="47.858px" stroke="#000000" stroke-width="1.4819" inkscape:export-filename="C:\Users\LURDES\Downloads\Bad Bunny\logo 1.png" inkscape:export-xdpi="278.00699" inkscape:export-ydpi="278.00699" xml:space="preserve"><tspan x="5.8197217" y="215.26418" stroke-width="1.4819" sodipodi:role="line">ARIAS SERVICE</tspan></text>
</g>
</svg>
  </div>
  <h1 class="titulo-principal">TuNoSaBeNa</h1>
</header>
  <section id="videos">
    <h2></h2>
    <div class="video-grid" id="videoGrid"></div>
  </section>

  <script>
    const videos = [
      "YSlpxMyVRbs",
    ];

    const videoGrid = document.getElementById("videoGrid");
    let currentVideo = null;

    videos.forEach(id => {
      const div = document.createElement("div");
      div.className = "video";
      div.innerHTML = `
        <div class="video-title">resiclar baterias</div>
        <img src="https://img.youtube.com/vi/${id}/hqdefault.jpg" alt="Video preview">
        <div class="play-button">▶️</div>
      `;
      div.addEventListener("click", () => {
        if (currentVideo && currentVideo !== div) {
          const prevId = currentVideo.dataset.id;
          currentVideo.innerHTML = `
            <img src="https://img.youtube.com/vi/${prevId}/hqdefault.jpg" alt="Video preview">
            <div class="play-button">▶️</div>
          `;
        }
        div.innerHTML = `
          <iframe width="100%" height="200" src="https://www.youtube.com/embed/${id}?autoplay=1"
            frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
        `;
        currentVideo = div;
      });
      div.dataset.id = id;
      videoGrid.appendChild(div);
    });

    const openChatBtn = document.getElementById('openChat');
    if (openChatBtn) {
      openChatBtn.addEventListener('click', () => {
        const container = document.getElementById('chatContainer');
        if (container) {
          container.style.display = container.style.display === 'none' ? 'block' : 'none';
        }
      });
    }

  </script>
</body>
</html>
