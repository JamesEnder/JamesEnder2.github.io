<!DOCTYPE html>
<html>
<head>
    <title>Manhwa List</title>
    <style>
        /* Global styles */
        body {
            text-align: center;
            background-color: #141414; /* Light grey background */
            font-family: Arial, sans-serif;
        }

        h2 {
            color: #5b0b73; /* Purple color for headers */
            font-size: 26px;
        }

        fieldset {
            border: 2px solid #5b0b73;
            border-radius: 10px;
            padding: 10px;
            margin: 10px 10px;
        }

        button {
            padding: 8px 16px;
            margin: 0 8px;
            font-size: 16px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            background-color: #8e44ad; /* Purple color */
            color: #fff;
        }

    </style>
</head>
<body>

    <fieldset id="firstFieldset">
        <div>
            <h2>I Reincarnated as a Legendary Surgeon</h2>
            <a href="https://rizzcomic.com/series/r2311170-i-reincarnated-as-a-legendary-surgeon">
                <img src="https://rizzcomic.com/assets/images/13__surgeon-20-06-2023_11_40_14_PM.webp" alt="I Reincarnated as a Legendary Surgeon" width="210" height="300">
            </a>
            <br>
            <strong id="chapters1" style="font-size: x-large;color:#5b0b73">95 Chapters</strong>
            <br><br>
            <button class="addBtn" style="width: 95px;">Add</button>
            <button class="subtractBtn" style="width: 95px;">Subtract</button>
            <br><br>

        </div>
    </fieldset>

    <fieldset id="secondFieldset">
        <div>
            <h2> Logging 10,000 Years into the Future</h2>
            <a href="https://drakescans.com/series/logging-10000-years-into-the-future/">
                <img src="https://drakescans.com/wp-content/uploads/2023/12/XTPSnDxOU-193x278.jpg" alt="Another Manhwa Title" width="210" height="300">
            </a>
            <br>
            <strong id="chapters2" style="font-size: x-large;color:#5b0b73">83 Chapters</strong>
            <br><br>
            <button class="addBtn" style="width: 95px;">Add</button>
            <button class="subtractBtn" style="width: 95px;">Subtract</button>
            <br><br>

        </div>
    </fieldset>

    <fieldset id="thirdFieldset">
        <div>
            <h2>Mixed Fantasy – My Journey To Become Invincible From Big-Spending Begins!</h2>
            <a href="https://nightscans.net/series/mixed-fantasy-my-journey-to-become-invincible-from-big-spending-begins/">
                <img src="https://nightscans.net/wp-content/uploads/2023/08/Mixed-Fantasy-My-Journey-To-Invincibility-Begins-By-Big-Spending_2.webp" alt="My Journey To Become Invincible From Big-Spending Begins!" width="210" height="300">
            </a>
            <br>
            <strong id="chapters3" style="font-size: x-large;color:#5b0b73">140 Chapters</strong>
            <br><br>
            <button class="addBtn" style="width: 95px;">Add</button>
            <button class="subtractBtn" style="width: 95px;">Subtract</button>
            <br><br>

        </div>
    </fieldset>

    <fieldset id="fourthFieldset">
        <div>
            <h2>Invincible After Shocking My Empress Wife</h2>
            <a href="https://drakescans.com/series/invincible-after-shocking-my-empress-wife/">
                <img src="https://drakescans.com/wp-content/uploads/2023/10/kvydCMYuz-193x278.jpg" alt="Invincible After Shocking My Empress Wife" width="210" height="300">
            </a>
            <br>
            <strong id="chapters4" style="font-size: x-large;color:#5b0b73">5 Chapters</strong>
            <br><br>
            <button class="addBtn" style="width: 95px;">Add</button>
            <button class="subtractBtn" style="width: 95px;">Subtract</button>
            <br><br>
        </div>
    </fieldset>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const chapters = [95, 83, 140, 5];
            const chaptersElements = document.querySelectorAll('[id^="chapters"]');
            const addBtns = document.querySelectorAll('.addBtn');
            const subtractBtns = document.querySelectorAll('.subtractBtn');

            // Initialize localStorage for each manhwa series if not already set
            for (let i = 0; i < chaptersElements.length; i++) {
                const storedChapterCount = localStorage.getItem(`chapters${i + 1}`);
                if (storedChapterCount === null || isNaN(parseInt(storedChapterCount))) {
                    localStorage.setItem(`chapters${i + 1}`, chapters[i]);
                }
            }

            // Retrieve saved chapter counts from localStorage on page load
            for (let i = 0; i < chaptersElements.length; i++) {
                const storedChapterCount = localStorage.getItem(`chapters${i + 1}`);
                if (storedChapterCount !== null) {
                    chapters[i] = parseInt(storedChapterCount);
                    chaptersElements[i].innerText = `${chapters[i]} Chapters`;
                }
            }

            addBtns.forEach((addBtn, index) => {
                addBtn.addEventListener('click', function() {
                    chapters[index]++;
                    chaptersElements[index].innerText = `${chapters[index]} Chapters`;
                    localStorage.setItem(`chapters${index + 1}`, chapters[index]);
                });
            });

            subtractBtns.forEach((subtractBtn, index) => {
                subtractBtn.addEventListener('click', function() {
                    if (chapters[index] > 0) {
                        chapters[index]--;
                        chaptersElements[index].innerText = `${chapters[index]} Chapters`;
                        localStorage.setItem(`chapters${index + 1}`, chapters[index]);
                    }
                });
            });
        });
    </script>
</body>
</html>
