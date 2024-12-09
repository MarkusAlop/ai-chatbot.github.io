<script>
    // You can add interactive features or data bindings here if needed
</script>

<style>
    :global(body) {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: 'Arial', sans-serif;
        overflow: hidden; /* Ensures no scrolling for full-page backgrounds */
    }

    .background {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100vh;
        background: linear-gradient(135deg, black, gray);
        overflow: hidden;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .circle {
        position: absolute;
        border-radius: 50%;
        background: rgba(255, 255, 255, 0.2);
        animation: float 8s ease-in-out infinite;
    }

    .circle:nth-child(1) {
        width: 200px;
        height: 200px;
        top: 10%;
        left: 15%;
    }

    .circle:nth-child(2) {
        width: 300px;
        height: 300px;
        top: 30%;
        left: 70%;
        animation-delay: 2s;
    }

    .circle:nth-child(3) {
        width: 150px;
        height: 150px;
        bottom: 20%;
        left: 40%;
        animation-delay: 4s;
    }

    .circle:nth-child(4) {
        width: 100px;
        height: 100px;
        top: 50%;
        left: 20%;
        animation-delay: 6s;
    }

    @keyframes float {
        0% {
            transform: translateY(0px);
        }
        50% {
            transform: translateY(-30px);
        }
        100% {
            transform: translateY(0px);
        }
    }

    .content {
        position: relative;
        z-index: 2;
        color: #fff;
        text-align: center;
        padding: 20px;
        font-size: 2rem;
    }

    .content h1 {
        margin: 0;
        font-size: 3rem;
    }

    .content p {
        margin: 10px 0 0;
        font-size: 1.5rem;
        color: rgba(255, 255, 255, 0.8);
    }
</style>

<div class="background">
    <div class="circle"></div>
    <div class="circle"></div>
    <div class="circle"></div>
    <div class="circle"></div>
    <div class="content">
        <h1>Welcome to the Chatbot!</h1>
        <p>Your friendly AI assistant is here to help.</p>
        <script src="https://cdn.botpress.cloud/webchat/v2.2/inject.js"></script>
        <script src="https://files.bpcontent.cloud/2024/12/07/15/20241207150207-TCTHZGMJ.js"></script>
    </div>
</div>
