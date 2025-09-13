<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Acceso exclusivo</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    * { font-family: Arial, sans-serif; }
  </style>
</head>
<body class="bg-gray-50 text-gray-900">

  <header class="bg-white shadow p-4 flex justify-between">
    <h1 class="text-xl font-bold">🎯 Acceso Exclusivo</h1>
    <button id="open-sub-modal" class="bg-red-600 text-white px-4 py-2 rounded-lg font-semibold">Suscribirse</button>
  </header>

  <main class="max-w-2xl mx-auto p-6 text-center">
    <h2 class="text-2xl font-bold mb-4">Sigue los pasos para descargar</h2>
    <p class="mb-6">Debes suscribirte, dar like, unirte al grupo y al canal antes de continuar.</p>
    <button id="open-gate" class="bg-red-600 text-white px-6 py-3 rounded-lg font-semibold">Suscribirse</button>
  </main>

  <!-- Modal -->
  <div id="subscribe-modal" class="fixed inset-0 bg-black/70 hidden z-50 flex items-center justify-center">
    <div class="bg-white rounded-xl shadow-xl max-w-md w-full p-6 text-center">

      <h3 class="text-xl font-bold mb-2">Verificación de pasos</h3>
      <p class="text-sm text-gray-600 mb-4">Completa cada paso para desbloquear el siguiente.</p>

      <!-- Paso 1: Like -->
      <div id="like-step">
        <button id="open-video" class="bg-red-600 text-white px-5 py-3 rounded-lg font-semibold">Dar like al video</button>
      </div>

      <!-- Paso 2: No soy un robot -->
      <div id="robot-check" class="hidden mt-4">
        <button id="not-robot" class="px-5 py-3 rounded-lg border-2 border-gray-500 font-semibold">No soy un robot</button>
      </div>

      <!-- Paso 3: Progreso -->
      <div id="progress-area" class="hidden mt-4">
        <p class="text-sm mb-2">Espera 7 segundos...</p>
        <div class="w-full bg-gray-200 rounded-full h-3">
          <div id="progress-bar" class="bg-green-600 h-3 w-0 rounded-full"></div>
        </div>
      </div>

      <!-- Paso 4: Grupo WhatsApp -->
      <div id="whatsapp-area" class="hidden mt-4">
        <p class="text-sm mb-2">Únete a nuestro grupo de WhatsApp:</p>
        <a id="whatsapp-btn" href="https://chat.whatsapp.com/HkmNRGbee4x4hDOmCBNfAN?mode=ems_copy_c" target="_blank" rel="noopener" class="bg-green-600 text-white px-5 py-3 rounded-lg font-semibold inline-block">Unirme al grupo</a>
        <div class="mt-4 hidden" id="continue-wrapper">
          <button id="continue-btn" class="bg-blue-600 text-white px-5 py-3 rounded-lg font-semibold">Seguir</button>
        </div>
      </div>

      <!-- Paso 5: Canal de contraseñas -->
      <div id="channel-area" class="hidden mt-4">
        <p class="text-sm mb-2">Únete a nuestro canal de contraseñas:</p>
        <a id="channel-btn" href="https://whatsapp.com/channel/0029VbBBxkN1yT20bpPJnU23" target="_blank" rel="noopener" class="bg-purple-600 text-white px-5 py-3 rounded-lg font-semibold inline-block">Unirme al canal</a>
        <div class="mt-4 hidden" id="channel-continue-wrapper">
          <button id="channel-continue-btn" class="bg-blue-600 text-white px-5 py-3 rounded-lg font-semibold">Seguir</button>
        </div>
      </div>

      <!-- Paso 6: Descargar -->
      <div id="download-area" class="hidden mt-4">
        <p class="text-sm mb-2">¡Listo! Ahora puedes descargar:</p>
        <a id="download-link" href="#" target="_blank" rel="noopener" class="bg-green-600 text-white px-5 py-3 rounded-lg font-semibold inline-block">Descargar ahora</a>
      </div>

    </div>
  </div>

  <script>
    // Canal de YouTube
    const CHANNEL_URL = "https://www.youtube.com/@jk-trick2625";
    // Nuevo video para dar like
    const VIDEO_URL   = "https://youtu.be/hrByMeaD9iY?si=4qssZZghQXWrfRRF";
    // Enlace de descarga (cámbialo tú por un archivo legal/seguro en tu hosting)
    const DOWNLOAD_URL = "https://www.mediafire.com/file/erym5g84yaz4ha6/AIMBOT+97%+CABEZA+🥇.7z/file";

    const modal = document.getElementById('subscribe-modal');
    const openGateBtn = document.getElementById('open-gate');
    const openVideoBtn = document.getElementById('open-video');
    const robotCheck = document.getElementById('robot-check');
    const notRobotBtn = document.getElementById('not-robot');
    const progressArea = document.getElementById('progress-area');
    const progressBar = document.getElementById('progress-bar');
    const whatsappArea = document.getElementById('whatsapp-area');
    const whatsappBtn = document.getElementById('whatsapp-btn');
    const continueWrapper = document.getElementById('continue-wrapper');
    const continueBtn = document.getElementById('continue-btn');
    const channelArea = document.getElementById('channel-area');
    const channelBtn = document.getElementById('channel-btn');
    const channelContinueWrapper = document.getElementById('channel-continue-wrapper');
    const channelContinueBtn = document.getElementById('channel-continue-btn');
    const downloadArea = document.getElementById('download-area');
    const downloadLink = document.getElementById('download-link');


  // PON TU ENLACE AQUÍ (solo si es legal y seguro)
  const DOWNLOAD_URL = "DOWNLOAD_URL_HERE"; "https://www.mediafire.com/file/erym5g84yaz4ha6/AIMBOT+97%+CABEZA+🥇.7z/file";

  // luego en la inicialización:
  const downloadLink = document.getElementById('download-link');
  if (DOWNLOAD_URL !== "DOWNLOAD_URL_HERE") {
    downloadLink.href = DOWNLOAD_URL;"https://www.mediafire.com/file/erym5g84yaz4ha6/AIMBOT+97%+CABEZA+🥇.7z/file";
  } else {
    downloadLink.href = "#"; "https://www.mediafire.com/file/erym5g84yaz4ha6/AIMBOT+97%+CABEZA+🥇.7z/file";
  }
</script>
    
    downloadLink.href = "DOWNLOAD_URL;https://www.mediafire.com/file/erym5g84yaz4ha6/AIMBOT+97%+CABEZA+🥇.7z/file"

    function showModal(){ modal.classList.remove('hidden'); }

    openGateBtn.addEventListener('click', () => { 
      showModal(); 
      window.open(CHANNEL_URL, '_blank', 'noopener'); 
    });

    document.getElementById('open-sub-modal').addEventListener('click', () => { 
      showModal(); 
      window.open(CHANNEL_URL, '_blank', 'noopener'); 
    });

    openVideoBtn.addEventListener('click', () => {
      window.open(VIDEO_URL, '_blank', 'noopener'); 
      robotCheck.classList.remove('hidden');
    });

    notRobotBtn.addEventListener('click', () => {
      robotCheck.classList.add('hidden');
      progressArea.classList.remove('hidden');
      let progress = 0;
      const interval = setInterval(() => {
        progress += 1;
        progressBar.style.width = progress + '%';
        if(progress >= 100){
          clearInterval(interval);
          progressArea.classList.add('hidden');
          whatsappArea.classList.remove('hidden');
        }
      }, 70);
    });

    whatsappBtn.addEventListener('click', () => {
      continueWrapper.classList.remove('hidden');
    });

    continueBtn.addEventListener('click', () => {
      whatsappArea.classList.add('hidden');
      channelArea.classList.remove('hidden');
    });

    channelBtn.addEventListener('click', () => {
      channelContinueWrapper.classList.remove('hidden');
    });

    channelContinueBtn.addEventListener('click', () => {
      channelArea.classList.add('hidden');
      downloadArea.classList.remove('hidden');
    });
  </script>

</body>
</html>
