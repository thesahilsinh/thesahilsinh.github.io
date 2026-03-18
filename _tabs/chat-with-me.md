---
layout: tab          # This makes it appear in the sidebar like other tabs
title: Chat With Me
icon: fas fa-comments
order: 6             # Puts it after ABOUT (change number if you want different position)
---

<!-- <div class="chat-page mt-8">
  <h1 class="text-3xl font-bold mb-2 flex items-center gap-3">
    hat With Me
  </h1>
  <p class="text-zinc-400 mb-8">
    Ask anything about my resume, PMA labs, Drone Forensics Tool, teaching experience, or malware analysis projects.<br>
    Powered by <strong>NVIDIA Llama 3.1</strong> — answers are grounded only in my content.
  </p> -->

  <!-- ChatGPT-style Full Chat Interface -->
 <!-- <div class="bg-zinc-900 border border-zinc-700 rounded-3xl shadow-2xl overflow-hidden max-w-4xl mx-auto" style="height: 620px; display: flex; flex-direction: column;">
    
    <!-- Chat Header -->
    <div class="bg-zinc-800 px-6 py-4 flex items-center justify-between border-b border-zinc-700">
      <div class="flex items-center gap-3">
        <img src="/assets/img/avatar.jpg" class="w-10 h-10 rounded-full ring-2 ring-[#00cc99]" alt="Sahilsinh">
        <div>
          <p class="font-bold text-white">Sahilsinh's AI Assistant</p>
          <p class="text-xs text-emerald-400">● Online • NVIDIA RAG</p>
        </div>
      </div>
      <span class="text-zinc-500 text-sm">Clear chat anytime ↓</span>
    </div>

    <!-- Messages Area (ChatGPT style) -->
    <div id="chat-messages" class="flex-1 p-6 overflow-y-auto bg-zinc-950 space-y-6 text-base">
      <!-- Messages appear here automatically -->
    </div>

    <!-- Input Bar (exactly like ChatGPT) -->
    <div class="p-5 border-t border-zinc-700 bg-zinc-900">
      <div class="flex gap-3">
        <input id="chat-input" 
               type="text" 
               placeholder="Ask me anything... (e.g. Tell me about your Drone Forensics Tool)"
               class="flex-1 bg-zinc-800 border border-zinc-700 focus:border-[#00cc99] focus:ring-2 focus:ring-[#00cc99] text-white placeholder-zinc-400 rounded-3xl px-6 py-4 outline-none">
        <button onclick="sendMessage()" 
                class="bg-[#00cc99] hover:bg-[#00b388] text-black font-bold px-8 rounded-3xl transition-all">
          Send
        </button>
      </div>
      <p class="text-[10px] text-zinc-500 text-center mt-3">Answers are based only on my resume + blog posts</p>
    </div>
<!--  </div>
</div>

<script>
  const apiUrl = "https://nvidia-rag-chatbox.onrender.com/chat";

  function addMessage(sender, text) {
    const container = document.getElementById("chat-messages");
    const div = document.createElement("div");
    div.className = sender === "user" ? "flex justify-end" : "flex justify-start";
    div.innerHTML = `
      <div class="${sender === "user" 
        ? 'bg-[#00cc99] text-black max-w-[75%]' 
        : 'bg-zinc-800 text-white max-w-[75%]'} px-5 py-3.5 rounded-3xl">
        ${text}
      </div>
    `;
    container.appendChild(div);
    container.scrollTop = container.scrollHeight;
    return div;
  }

  async function sendMessage() {
    const input = document.getElementById("chat-input");
    const msg = input.value.trim();
    if (!msg) return;

    addMessage("user", msg);
    input.value = "";

    const loading = addMessage("bot", "Thinking...");

    try {
      const res = await fetch(apiUrl, {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ message: msg })
      });
      const data = await res.json();
      loading.remove();
      addMessage("bot", data.response || data.answer || "No answer received.");
    } catch (e) {
      loading.remove();
      addMessage("bot", " Backend is waking up. Refresh and try again in 20 seconds.");
    }
  }

  // Enter key support
  document.getElementById("chat-input").addEventListener("keypress", function(e) {
    if (e.key === "Enter") sendMessage();
  });

  // Optional: Welcome message on page load
  window.onload = function() {
    const container = document.getElementById("chat-messages");
    if (container.children.length === 0) {
      const welcome = document.createElement("div");
      welcome.innerHTML = `
        <div class="bg-zinc-800 text-white max-w-[75%] px-5 py-3.5 rounded-3xl">
          Hi! I'm your personal AI assistant. Ask me anything about Sahilsinh's resume, malware analysis labs, or projects 
        </div>`;
      container.appendChild(welcome);
    }
  };
</script>
