DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Catálogo de Fotos</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 20px;
      background-color: #f9f9f9;
    }
    h1 {
      text-align: center;
      color: #333;
    }
    .catalogo {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
    }
    .item {
      background: white;
      border: 1px solid #ccc;
      border-radius: 10px;
      padding: 10px;
      width: 220px;
      text-align: center;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .item img {
      width: 200px;
      height: auto;
      border-radius: 5px;
    }
    .qr {
      margin-top: 10px;
    }
    .link {
      display: block;
      margin-top: 10px;
      color: #0066cc;
      text-decoration: none;
    }
    .link:hover {
      text-decoration: underline;
    }
  </style>
</head>
<body>

  <h1>Catálogo de Fotos</h1>

  <div class="catalogo" id="catalogo">
    <!-- Os itens serão adicionados dinamicamente -->
  </div>

  <script>
    // Lista de itens do catálogo
    const itens = [
      {
        imagem: "https://via.placeholder.com/200x150?text=Foto+1",
        link: "https://exemplo.com/foto1"
      },
      {
        imagem: "https://via.placeholder.com/200x150?text=Foto+2",
        link: "https://exemplo.com/foto2"
      },
      {
        imagem: "https://via.placeholder.com/200x150?text=Foto+3",
        link: "https://exemplo.com/foto3"
      }
    ];

    const container = document.getElementById("catalogo");

    itens.forEach((item, i) => {
      const div = document.createElement("div");
      div.className = "item";

      // Adiciona a imagem
      const img = document.createElement("img");
      img.src = item.imagem;
      div.appendChild(img);

      // Adiciona o link
      const a = document.createElement("a");
      a.href = item.link;
      a.textContent = "Ver mais";
      a.className = "link";
      a.target = "_blank";
      div.appendChild(a);

      // Adiciona o QR Code
      const qr = document.createElement("img");
      qr.className = "qr";
      qr.src = `https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=${encodeURIComponent(item.link)}`;
      div.appendChild(qr);

      container.appendChild(div);
    });
  </script>

</body>
</html
