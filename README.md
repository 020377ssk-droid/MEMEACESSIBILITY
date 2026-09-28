# MEMEACESSIBILITY
https://lens-explain-web-app-bso7.bolt.host
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <title>MemeLens — See the Joke</title>

    <link
        rel="stylesheet"
        href="style.css"
    >
</head>

<body>

<!-- ================= NAVBAR ================= -->

<nav class="navbar">

    <div class="brand">

        <div class="brand-icon">
            M
        </div>

        <div class="brand-name">
            MemeLens
        </div>

        <div class="brand-subtitle">
            / see the joke
        </div>

    </div>


    <div class="nav-links">

        <button
            class="nav-btn active"
            onclick="showPage('analyze')"
        >
            ◉ Analyze
        </button>

        <button
            class="nav-btn"
            onclick="showPage('create')"
        >
            ＋ Create
        </button>

        <button
            class="nav-btn"
            onclick="showPage('history')"
        >
            ◷ History
        </button>

        <button
            class="nav-btn"
            onclick="showPage('model')"
        >
            ⚙ AI Model
        </button>

    </div>


    <button
        class="accessibility-btn"
        onclick="toggleAccessibility()"
    >
        ♿ Accessibility
    </button>

</nav>


<!-- ================= ANALYZE PAGE ================= -->

<main
    id="analyzePage"
    class="page"
>

    <section class="hero">

        <h1>
            Understand any meme.
        </h1>

        <p>
            Upload a meme or pick a demo, and MemeLens reads the text,
            explains what it means, why it's funny, and the cultural
            context behind it — with audio narration and translations
            into Hindi and Marathi.
        </p>

    </section>


    <section class="workspace">

        <!-- LEFT SIDE -->

        <div class="panel upload-panel">

            <div class="panel-title">
                <span>▣</span>
                Meme image
            </div>


            <div
                id="dropZone"
                class="drop-zone"
                onclick="document.getElementById('fileInput').click()"
            >

                <div class="upload-icon">
                    ⇧
                </div>

                <div class="upload-title">
                    Click to upload or drag a meme image here
                </div>

                <div class="upload-subtitle">
                    PNG, JPG, or WEBP — analyzed entirely in your browser
                </div>

                <input
                    type="file"
                    id="fileInput"
                    accept="image/png,image/jpeg,image/webp"
                    hidden
                >

            </div>


            <div
                id="previewContainer"
                class="preview-container hidden"
            >

                <img
                    id="previewImage"
                    src=""
                    alt="Uploaded meme"
                >

                <button
                    class="secondary-btn"
                    onclick="removeImage()"
                >
                    Remove image
                </button>

            </div>

        </div>


        <!-- RIGHT SIDE -->

        <div class="panel demo-panel">

            <div class="panel-title">
                <span class="sparkle">✧</span>
                Analyze
            </div>

            <p class="section-label">
                Try a demo or your own meme:
            </p>


            <div class="demo-grid">

                <div
                    class="demo-card"
                    onclick="loadDemo('grumpy')"
                >

                    <img
                        src="images/grumpy-cat.jpg"
                        alt="Grumpy Cat meme"
                    >

                    <strong>
                        Grumpy Cat
                    </strong>

                    <small>
                        Built-in demo
                    </small>

                </div>


                <div
                    class="demo-card"
                    onclick="loadDemo('walking')"
                >

                    <img
                        src="images/walking-away.jpg"
                        alt="Walking Away meme"
                    >

                    <strong>
                        Walking Away
                    </strong>

                    <small>
                        Built-in demo
                    </small>

                </div>


                <div
                    class="demo-card"
                    onclick="loadDemo('overworked')"
                >

                    <img
                        src="images/overworked.jpg"
                        alt="Overworked meme"
                    >

                    <strong>
                        Overworked
                    </strong>

                    <small>
                        Built-in demo
                    </small>

                </div>

            </div>


            <p class="section-label your-memes">
                Your memes:
            </p>


            <div class="demo-grid">

                <div
                    class="demo-card"
                    onclick="loadDemo('meme1')"
                >

                    <img
                        src="images/meme1.jpg"
                        alt="Custom meme"
                    >

                    <strong>
                        Meme 1
                    </strong>

                </div>


                <div
                    class="demo-card"
                    onclick="loadDemo('meme2')"
                >

                    <img
                        src="images/meme2.jpg"
                        alt="Custom meme"
                    >

                    <strong>
                        Meme 2
                    </strong>

                </div>


                <div
                    class="demo-card"
                    onclick="loadDemo('meme3')"
                >

                    <img
                        src="images/meme3.jpg"
                        alt="Custom meme"
                    >

                    <strong>
                        Meme 3
                    </strong>

                </div>

            </div>

        </div>

    </section>


    <!-- ================= RESULTS ================= -->

    <section
        id="results"
        class="results hidden"
    >

        <div class="result-card">

            <div class="result-header">

                <h2>
                    DETECTED TEXT
                </h2>

                <button
                    class="listen-btn"
                    onclick="speak('detectedText')"
                >
                    🔊 Listen
                </button>

            </div>

            <p id="detectedText">
                Walking away from my responsibilities
            </p>

        </div>


        <div class="result-card">

            <div class="result-header">

                <h2>
                    WHAT YOU SEE
                </h2>

                <button
                    class="listen-btn"
                    onclick="speak('whatYouSee')"
                >
                    🔊 Listen
                </button>

            </div>

            <p id="whatYouSee">
                A young couple walks together on a city sidewalk.
                The image has white impact-font text at the top
                reading "ME WALKING AWAY FROM MY RESPONSIBILITIES."
            </p>

        </div>


        <div class="result-card">

            <div class="result-header">

                <h2>
                    WHAT THE MEME MEANS
                </h2>

                <button
                    class="listen-btn"
                    onclick="speak('meaning')"
                >
                    🔊 Listen
                </button>

            </div>

            <p id="meaning">
                The image is staged as a relatable meme about
                avoiding tasks or obligations. The person walking
                confidently represents the meme creator playfully
                abandoning their duties.
            </p>

        </div>


        <div class="result-card">

            <div class="result-header">

                <h2>
                    WHY IT IS FUNNY
                </h2>

                <button
                    class="listen-btn"
                    onclick="speak('funny')"
                >
                    🔊 Listen
                </button>

            </div>

            <p id="funny">
                It takes an ordinary, neutral photo and overlays
                an aspirational caption. The humor is in projecting
                confidence onto a mundane scene — the person looks
                purposeful, but the "purpose" is actually running
                away from responsibility.
            </p>

        </div>


        <div class="result-card">

            <div class="result-header">

                <h2>
                    CULTURAL CONTEXT
                </h2>

                <button
                    class="listen-btn"
                    onclick="speak('culture')"
                >
                    🔊 Listen
                </button>

            </div>

            <p id="culture">
                This follows the "me walking away from" meme
                template popular on social media, where a photo
                of someone walking is captioned with something
                they're avoiding. It is part of the broader
                self-deprecating humor genre about procrastination
                and avoidance.
            </p>

        </div>


        <!-- LANGUAGE -->

        <div class="language-card">

            <h2>
                🌐 TRANSLATIONS
            </h2>


            <div class="translation-grid">

                <div>

                    <h3>
                        🇮🇳 Hindi
                    </h3>

                    <p id="hindi">
                        मैं अपनी जिम्मेदारियों से दूर जा रहा हूँ।
                    </p>

                    <button
                        class="small-btn"
                        onclick="speakText(
                            'मैं अपनी जिम्मेदारियों से दूर जा रहा हूँ'
                        )"
                    >
                        🔊
                    </button>

                </div>


                <div>

                    <h3>
                        🇮🇳 Marathi
                    </h3>

                    <p id="marathi">
                        मी माझ्या जबाबदाऱ्यांपासून दूर जात आहे.
                    </p>

                    <button
                        class="small-btn"
                        onclick="speakText(
                            'मी माझ्या जबाबदाऱ्यांपासून दूर जात आहे'
                        )"
                    >
                        🔊
                    </button>

                </div>

            </div>

        </div>

    </section>

</main>


<!-- ================= CREATE PAGE ================= -->

<main
    id="createPage"
    class="page hidden"
>

    <section class="hero">

        <h1>
            Create a meme.
        </h1>

        <p>
            Add your own image and caption to create an accessible meme.
        </p>

    </section>


    <div class="create-container">

        <div class="create-preview">

            <div id="memeCanvas">

                <span id="canvasText">
                    YOUR MEME
                </span>

            </div>

        </div>


        <div class="create-controls">

            <label>
                Upload image
            </label>

            <input
                type="file"
                id="createImage"
                accept="image/*"
            >


            <label>
                Meme text
            </label>

            <textarea
                id="memeText"
                placeholder="Enter your meme text..."
            ></textarea>


            <label>
                Text color
            </label>

            <input
                type="color"
                id="textColor"
                value="#ffffff"
            >


            <button
                class="primary-btn"
                onclick="updateMeme()"
            >
                Update Meme
            </button>

        </div>

    </div>

</main>


<!-- ================= HISTORY ================= -->

<main
    id="historyPage"
    class="page hidden"
>

    <section class="hero">

        <h1>
            Analysis history.
        </h1>

        <p>
            Previously analyzed memes appear here.
        </p>

    </section>


    <div
        id="historyList"
        class="history-list"
    >

        <div class="empty-history">

            <div>
                ◷
            </div>

            <h2>
                No history yet
            </h2>

            <p>
                Analyze a meme and it will appear here.
            </p>

        </div>

    </div>

</main>


<!-- ================= AI MODEL ================= -->

<main
    id="modelPage"
    class="page hidden"
>

    <section class="hero">

        <h1>
            AI Model
        </h1>

        <p>
            MemeLens uses a multimodal pipeline to understand
            meme images and generate accessibility descriptions.
        </p>

    </section>


    <div class="model-grid">

        <div class="model-card">

            <div class="model-icon">
                OCR
            </div>

            <h2>
                Text Detection
            </h2>

            <p>
                Detects and extracts text embedded inside meme images.
            </p>

        </div>


        <div class="model-card">

            <div class="model-icon">
                👁
            </div>

            <h2>
                Visual Understanding
            </h2>

            <p>
                Identifies important objects, people, actions and
                visual relationships.
            </p>

        </div>


        <div class="model-card">

            <div class="model-icon">
                🧠
            </div>

            <h2>
                Meme Understanding
            </h2>

            <p>
                Combines visual information and text to explain
                the meaning and humor.
            </p>

        </div>


        <div class="model-card">

            <div class="model-icon">
                🔊
            </div>

            <h2>
                Accessibility
            </h2>

            <p>
                Converts explanations into audio for users who
                benefit from screen-free access.
            </p>

        </div>

    </div>

</main>


<!-- ================= ACCESSIBILITY PANEL ================= -->

<div
    id="accessibilityPanel"
    class="accessibility-panel hidden"
>

    <div class="accessibility-header">

        <h2>
            Accessibility
        </h2>

        <button
            onclick="toggleAccessibility()"
        >
            ×
        </button>

    </div>


    <button onclick="increaseFont()">
        A+ Increase text
    </button>

    <button onclick="decreaseFont()">
        A− Decrease text
    </button>

    <button onclick="toggleContrast()">
        ◐ High contrast
    </button>

    <button onclick="toggleDyslexia()">
        Aa Reading font
    </button>

    <button onclick="speakPage()">
        🔊 Read page
    </button>

</div>


<script src="script.js"></script>

</body>

</html>
