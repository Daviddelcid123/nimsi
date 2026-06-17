# nimsi/**
 * @name NIMSI Purple Glass
 * @author Josue
 * @version 1.0.0
 * @description Tema transparente lila con logo NIMSI
 * @website https://github.com/TU-USUARIO
 * @source https://github.com/TU-USUARIO/NIMSI-Theme
 */

/* ==========================================
   CONFIGURACIÓN EDITABLE
========================================== */

:root{

    /* URL DEL LOGO NIMSI */
   [ --nimsi-logo: url("AQUI_PEGA_LA_URL_DE_TU_IMAGEN");](https://github.com/Daviddelcid123/nimsi-logo.png/blob/main/Dise%C3%B1o%20navis%2C%2016%20cm%20de%20largo%20X%205%20cm%20de%20ancho.png)

    /* COLORES */
    --accent-purple: #b388ff;
    --accent-pink: #f4b6ff;
    --accent-dark: #1b1233;

    /* TRANSPARENCIA */
    --glass-opacity: .30;
    --blur-strength: 18px;

    /* TAMAÑO DEL LOGO */
    --logo-size: 65%;

    /* BRILLO */
    --glow-color: rgba(179,136,255,.65);
}

/* ==========================================
   FONDO GENERAL
========================================== */

body,
.appMount,
.bg__960e4,
.layer__960e4{

    background:
        linear-gradient(
            135deg,
            rgba(15,10,35,.90),
            rgba(45,20,80,.90)
        ) !important;
}

/* ==========================================
   LOGO NIMSI FONDO
========================================== */

.appMount::before{

    content:"";

    position:fixed;
    inset:0;

    background-image:var(--nimsi-logo);
    background-repeat:no-repeat;
    background-position:center;
    background-size:var(--logo-size);

    opacity:.22;

    filter:
        drop-shadow(0 0 25px var(--glow-color))
        drop-shadow(0 0 50px var(--glow-color));

    pointer-events:none;
    z-index:0;
}

/* ==========================================
   EFECTO CRISTAL
========================================== */

[class*="sidebar"],
[class*="container"],
[class*="chat"],
[class*="content"],
[class*="members"],
[class*="panels"]{

    background:
        rgba(20,15,40,var(--glass-opacity))
        !important;

    backdrop-filter:
        blur(var(--blur-strength))
        !important;

    -webkit-backdrop-filter:
        blur(var(--blur-strength))
        !important;

    border:
        1px solid rgba(255,255,255,.08);

    border-radius:16px;
}

/* ==========================================
   BOTONES
========================================== */

button{

    transition:.25s ease!important;
}

button:hover{

    transform:translateY(-2px);

    box-shadow:
        0 0 12px var(--accent-purple),
        0 0 30px var(--accent-pink);
}

/* ==========================================
   CANAL SELECCIONADO
========================================== */

[class*="modeSelected"]{

    background:
        linear-gradient(
            90deg,
            rgba(179,136,255,.20),
            rgba(244,182,255,.20)
        ) !important;

    border-left:
        4px solid var(--accent-purple);

    border-radius:12px;
}

/* ==========================================
   TEXTO
========================================== */

[class*="messageContent"],
[class*="markup"],
[class*="username"],
[class*="title"]{

    color:white!important;
}

/* ==========================================
   INPUT CHAT
========================================== */

form{

    background:
        rgba(255,255,255,.05)
        !important;

    border-radius:18px!important;

    border:
        1px solid rgba(255,255,255,.08);
}

/* ==========================================
   AVATARES
========================================== */

[class*="avatar"]{

    box-shadow:
        0 0 10px var(--accent-purple),
        0 0 20px rgba(179,136,255,.35);
}

/* ==========================================
   SCROLLBAR
========================================== */

::-webkit-scrollbar-thumb{

    background:
        linear-gradient(
            var(--accent-pink),
            var(--accent-purple)
        );

    border-radius:20px;
}
