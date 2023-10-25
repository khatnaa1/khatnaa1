<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Candle</title>
    <style>
        body {
            margin: 0;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: black;
        }
        .candle {
            width: 15em;
            height: 30em;
            font-size: 7px;
            background: linear-gradient(
                orange,
                darkorange,
                sienna,
                saddlebrown 50%,
                rgba(0,0,0,0.6)
            );
            box-shadow: 
            inset 2em -3em 5em rgba(0,0,0,0.6),
            inset -2em 0 5em rgba(0, 0, 0, 0.6);
            border-radius: 10em / 4em ;
            position: relative;
            display: flex;
            justify-content: center;
            top: 10em;
        }
        .candle::before {
            content: '';
            position: absolute;
            width: inherit;
            height: 5em;
            border: 0.2em solid darkorange;
            border-radius: 50%;
            box-sizing: border-box;
            background: radial-gradient(
                #444,
                orange,
                saddlebrown,
                sienna,
                darkorange,
            );
            filter: opacity(0.7);
        }
        .thread {
            position: absolute;
            width: 0.6em;
            height: 3.6em;
            top: -1.8em;
            background: linear-gradient(
                #111,
                black,
                orange 90%
            );
            border-radius: 40% 40% 0 0;
        }
        .flames {
            position: absolute;
            width: 2.4em;
        }
        .flames::before {
            content: '';
            position: absolute;
            width: inherit;
            height: 6em;
            background-color: royalblue;
            top: -4.8em;
            border-radius: 50% 50% 35% 35%;
            border: 0.2em solid dodgerblue;
            box-sizing: border-box;
            filter: opacity(0.7);
        }
        .flames::after {
            content: '';
            position: absolute;
            width: inherit;
            height: 12em;
            top: -12em;
            background: linear-gradient(white 50% , transparent);
            border-radius: 50% 50% 20% 20%;
            box-shadow: 0 -0.6em 0.4em darkorange;
            animation: 
            move 6s linear infinite;
            /* animation: grow 5s linear infinite ; */
        }
        @keyframes move {
            0%, 100% {
                transform: rotate(2deg);
            }
            50% {
                transform: rotate(-2deg);
            }
        }
        /* @keyframes grow {
            0%, 100% {
                height: 12em;
                top: -12em;
            }
            50% {
                height: 14em;
                top: -13em;
            }
        } */
        .glow {
            position:absolute;
            width: 10em;
            height: 18em;
            background-color: orangered;
            border-radius: 50%;
            top: -17em;
            filter: blur(6em);
            animation: blink 100ms infinite;
        }
        @keyframes blink {
            to {
                filter: blur(6em) opacity(00.2em);
            }
        }
    </style>
</head>
<body>
    <div class="candle">
        <span class="glow"></span>
        <span class="flames"></span>
        <span class="thread"></span>
    </div>
</body>
</html>
