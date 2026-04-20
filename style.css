const settingsBtn = document.getElementById('settingsBtn');
const closeModal = document.getElementById('closeModal');
const overlay = document.getElementById('settingsOverlay');
const applyBtn = document.getElementById('applyBtn');
const playBtn = document.getElementById('playBtn');
const previewBtn = document.getElementById('previewBtn');
const musicSelect = document.getElementById('musicSelect');
const audio = document.getElementById('bgAudio');
const rain = document.querySelector('.rain');
const rainTextInput = document.getElementById('rainText');
const color1 = document.getElementById('color1');
const color2 = document.getElementById('color2');
const mainText = document.getElementById('mainText');
const mainTextInput = document.getElementById('mainTextInput');
const mainColor = document.getElementById('mainColor');
const book = document.getElementById('book');
const bookToggle = document.getElementById('bookToggle');
const heartToggle = document.getElementById('heartToggle');

settingsBtn.addEventListener('click', () => overlay.classList.remove('hidden'));
closeModal.addEventListener('click', () => overlay.classList.add('hidden'));
overlay.addEventListener('click', (e) => {
  if (e.target === overlay) overlay.classList.add('hidden');
});

function buildRain() {
  rain.innerHTML = '';
  const words = rainTextInput.value.split('|').map((w) => w.trim()).filter(Boolean);
  const picks = words.length ? words : ['HAPPY BIRTHDAY'];

  for (let i = 0; i < 55; i += 1) {
    const span = document.createElement('span');
    span.textContent = picks[i % picks.length];
    span.style.left = `${Math.random() * 100}%`;
    span.style.animationDuration = `${5 + Math.random() * 8}s`;
    span.style.animationDelay = `${Math.random() * 4}s`;
    span.style.color = i % 2 === 0 ? color1.value : color2.value;
    rain.appendChild(span);
  }
}

function applySettings() {
  mainText.textContent = mainTextInput.value || 'A Special Gift For You';
  mainText.style.color = mainColor.value;
  book.classList.toggle('hidden', !bookToggle.checked);
  rain.style.display = heartToggle.checked ? 'block' : 'none';
  buildRain();
  overlay.classList.add('hidden');
}

function setAudio() {
  if (musicSelect.value) {
    audio.src = musicSelect.value;
  }
}

previewBtn.addEventListener('click', async () => {
  setAudio();
  if (!audio.src) return;
  await audio.play().catch(() => {});
});

playBtn.addEventListener('click', async () => {
  setAudio();
  if (!audio.src) return;
  if (audio.paused) {
    await audio.play().catch(() => {});
    playBtn.textContent = '⏸';
  } else {
    audio.pause();
    playBtn.textContent = '▶';
  }
});

applyBtn.addEventListener('click', applySettings);
window.addEventListener('resize', buildRain);
buildRain();
