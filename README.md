# Watch-and-win
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>FreelanceHub - Find Freelancers & Clients</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    body {
      background: #f5f7fb;
      color: #222;
    }

    header {
      background: #111827;
      color: white;
      padding: 16px 5%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .logo {
      font-size: 24px;
      font-weight: bold;
    }

    nav a {
      color: white;
      text-decoration: none;
      margin-left: 20px;
      font-size: 15px;
    }

    nav a:hover {
      color: #60a5fa;
    }

    .hero {
      text-align: center;
      padding: 80px 20px;
      background: linear-gradient(135deg, #2563eb, #4f46e5);
      color: white;
    }

    .hero h1 {
      font-size: 42px;
      margin-bottom: 15px;
    }

    .hero p {
      font-size: 18px;
      margin-bottom: 30px;
    }

    .search-box {
      max-width: 650px;
      margin: auto;
      display: flex;
      background: white;
      border-radius: 8px;
      overflow: hidden;
    }

    .search-box input {
      flex: 1;
      padding: 15px;
      border: none;
      outline: none;
      font-size: 16px;
    }

    .search-box button {
      background: #111827;
      color: white;
      border: none;
      padding: 15px 25px;
      cursor: pointer;
    }

    .section {
      padding: 50px 5%;
    }

    .section h2 {
      text-align: center;
      margin-bottom: 30px;
      font-size: 30px;
    }

    .categories {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 15px;
      max-width: 1000px;
      margin: auto;
    }

    .category {
      background: white;
      padding: 25px 15px;
      text-align: center;
      border-radius: 10px;
      box-shadow: 0 3px 12px rgba(0,0,0,0.08);
      cursor: pointer;
    }

    .category:hover {
      transform: translateY(-3px);
    }

    .freelancers {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      max-width: 1100px;
      margin: auto;
    }

    .card {
      background: white;
      border-radius: 12px;
      padding: 25px;
      box-shadow: 0 3px 15px rgba(0,0,0,0.08);
    }

    .avatar {
      width: 70px;
      height: 70px;
      background: #2563eb;
      color: white;
      border-radius: 50%;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 25px;
      margin-bottom: 15px;
    }

    .card h3 {
      margin-bottom: 8px;
    }

    .card p {
      color: #666;
      margin-bottom: 10px;
    }

    .rating {
      color: #f59e0b;
      margin-bottom: 15px;
    }

    .btn {
      border: none;
      background: #2563eb;
      color: white;
      padding: 11px 18px;
      border-radius: 6px;
      cursor: pointer;
    }

    .btn:hover {
      background: #1d4ed8;
    }

    .security {
      background: #111827;
      color: white;
      text-align: center;
      padding: 55px 20px;
    }

    .security h2 {
      margin-bottom: 20px;
    }

    .security-items {
      display: flex;
      justify-content: center;
      gap: 25px;
      flex-wrap: wrap;
    }

    .security-item {
      max-width: 220px;
      padding: 20px;
    }

    footer {
      background: #0b1120;
      color: #aaa;
      text-align: center;
      padding: 25px;
    }

    /* Modal */

    .modal {
      display: none;
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.6);
      justify-content: center;
      align-items: center;
      z-index: 200;
    }

    .modal-box {
      background: white;
      width: 90%;
      max-width: 450px;
      padding: 30px;
      border-radius: 12px;
    }

    .modal-box h2 {
      margin-bottom: 20px;
    }

    .modal-box input,
    .modal-box textarea {
      width: 100%;
      padding: 12px;
      margin-bottom: 12px;
      border: 1px solid #ddd;
      border-radius: 6px;
      outline: none;
    }

    .close {
      float: right;
      font-size: 25px;
      cursor: pointer;
    }

    .chat {
      margin-top: 20px;
      border-top: 1px solid #ddd;
      padding-top: 15px;
    }

    .chat-message {
      background: #eef2ff;
      padding: 10px;
      border-radius: 6px;
      margin-bottom: 8px;
    }

    @media(max-width:600px) {
      .hero h1 {
        font-size: 30px;
      }

      nav {
        display: none;
      }

      .search-box {
        flex-direction: column;
      }

      .search-box button {
        width: 100%;
      }
    }
  </style>
</head>

<body>

<header>
  <div class="logo">FreelanceHub</div>

  <nav>
    <a href="#home">Home</a>
    <a href="#freelancers">Freelancers</a>
    <a href="#security">Safety</a>
    <a href="#" onclick="openModal()">Join</a>
  </nav>
</header>


<section class="hero" id="home">

  <h1>Find Talent. Get Work.</h1>

  <p>
    Connect freelancers and clients from around the world.
  </p>

  <div class="search-box">
    <input
      type="text"
      id="searchInput"
      placeholder="Search for a service..."
    >

    <button onclick="searchFreelancers()">
      Search
    </button>
  </div>

</section>


<section class="section">

  <h2>Popular Services</h2>

  <div class="categories">

    <div class="category" onclick="filterCategory('Web Development')">
      💻<br><br>
      Web Development
    </div>

    <div class="category" onclick="filterCategory('Graphic Design')">
      🎨<br><br>
      Graphic Design
    </div>

    <div class="category" onclick="filterCategory('Video Editing')">
      🎬<br><br>
      Video Editing
    </div>

    <div class="category" onclick="filterCategory('Writing')">
      ✍️<br><br>
      Writing
    </div>

    <div class="category" onclick="filterCategory('Marketing')">
      📢<br><br>
      Marketing
    </div>

    <div class="category" onclick="filterCategory('Data Entry')">
      📊<br><br>
      Data Entry
    </div>

  </div>

</section>


<section class="section" id="freelancers">

  <h2>Featured Freelancers</h2>

  <div class="freelancers" id="freelancerList">

    <div class="card" data-category="Web Development">

      <div class="avatar">JD</div>

      <h3>John Developer</h3>

      <p>Web Developer</p>

      <div class="rating">
        ★★★★★ 4.9
      </div>

      <p>
        I create modern responsive websites for businesses.
      </p>

      <button class="btn"
        onclick="openChat('John Developer')">
        Chat with Freelancer
      </button>

    </div>


    <div class="card" data-category="Graphic Design">

      <div class="avatar">AM</div>

      <h3>Anna Miller</h3>

      <p>Graphic Designer</p>

      <div class="rating">
        ★★★★★ 4.8
      </div>

      <p>
        Professional logos, flyers and social media designs.
      </p>

      <button class="btn"
        onclick="openChat('Anna Miller')">
        Chat with Freelancer
      </button>

    </div>


    <div class="card" data-category="Video Editing">

      <div class="avatar">MK</div>

      <h3>Mike Creative</h3>

      <p>Video Editor</p>

      <div class="rating">
        ★★★★★ 4.9
      </div>

      <p>
        Short-form videos, advertisements and social media content.
      </p>

      <button class="btn"
        onclick="openChat('Mike Creative')">
        Chat with Freelancer
      </button>

    </div>


    <div class="card" data-category="Writing">

      <div class="avatar">SA</div>

      <h3>Sarah Writer</h3>

      <p>Content Writer</p>

      <div class="rating">
        ★★★★★ 4.7
      </div>

      <p>
        Articles, website content and product descriptions.
      </p>

      <button class="btn"
        onclick="openChat('Sarah Writer')">
        Chat with Freelancer
      </button>

    </div>

  </div>

</section>


<section class="security" id="security">

  <h2>Built With Safety in Mind</h2>

  <div class="security-items">

    <div class="security-item">
      🔒
      <h3>Secure Accounts</h3>
      <p>
        Account security features help protect users.
      </p>
    </div>

    <div class="security-item">
      🛡️
      <h3>Report Scams</h3>
      <p>
        Users can report suspicious accounts and activity.
      </p>
    </div>

    <div class="security-item">
      💬
      <h3>Platform Chat</h3>
      <p>
        Clients and freelancers can communicate through the platform.
      </p>
    </div>

    <div class="security-item">
      💳
      <h3>Protected Payments</h3>
      <p>
        Payment protection can be added when a payment system is connected.
      </p>
    </div>

  </div>

</section>


<footer>

  <p>
    © 2026 FreelanceHub. All rights reserved.
  </p>

</footer>


<!-- JOIN MODAL -->

<div class="modal" id="joinModal">

  <div class="modal-box">

    <span class="close" onclick="closeModal()">×</span>

    <h2>Create Account</h2>

    <input
      type="text"
      placeholder="Full name"
    >

    <input
      type="email"
      placeholder="Email address"
    >

    <input
      type="password"
      placeholder="Password"
    >

    <button class="btn" onclick="createAccount()">
      Create Account
    </button>

  </div>

</div>


<!-- CHAT MODAL -->

<div class="modal" id="chatModal">

  <div class="modal-box">

    <span class="close" onclick="closeChat()">×</span>

    <h2 id="chatTitle">
      Chat
    </h2>

    <div class="chat" id="messages">

      <div class="chat-message">
        Hello! How can I help you?
      </div>

    </div>

    <br>

    <input
      type="text"
      id="messageInput"
      placeholder="Type your message..."
    >

    <button
      class="btn"
      onclick="sendMessage()">
      Send
    </button>

  </div>

</div>


<script>

  function openModal() {
    document.getElementById("joinModal").style.display = "flex";
  }

  function closeModal() {
    document.getElementById("joinModal").style.display = "none";
  }

  function createAccount() {
    alert("Account registration demo. A real database is required for real accounts.");
  }


  function openChat(name) {

    document.getElementById("chatTitle").innerText =
      "Chat with " + name;

    document.getElementById("chatModal").style.display = "flex";

  }


  function closeChat() {

    document.getElementById("chatModal").style.display = "none";

  }


  function sendMessage() {

    const input =
      document.getElementById("messageInput");

    const message =
      input.value.trim();

    if (message === "") {
      return;
    }

    const messageBox =
      document.createElement("div");

    messageBox.className =
      "chat-message";

    messageBox.innerText =
      message;

    document.getElementById("messages")
      .appendChild(messageBox);

    input.value = "";

  }


  function searchFreelancers() {

    const search =
      document.getElementById("searchInput")
      .value
      .toLowerCase();

    const cards =
      document.querySelectorAll(".card");

    cards.forEach(card => {

      const text =
        card.innerText.toLowerCase();

      if (text.includes(search)) {
        card.style.display = "block";
      } else {
        card.style.display = "none";
      }

    });

  }


  function filterCategory(category) {

    const cards =
      document.querySelectorAll(".card");

    cards.forEach(card => {

      if (card.dataset.category === category) {
        card.style.display = "block";
      } else {
        card.style.display = "none";
      }

    });

    document.getElementById("freelancers")
      .scrollIntoView({
        behavior: "smooth"
      });

  }


  window.onclick = function(event) {

    const joinModal =
      document.getElementById("joinModal");

    const chatModal =
      document.getElementById("chatModal");

    if (event.target === joinModal) {
      closeModal();
    }

    if (event.target === chatModal) {
      closeChat();
    }

  }

</script>

</body>
</html>
