<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Accesorios Tecnológicos</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/tailwindcss/2.2.19/tailwind.min.js"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css"/>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        body {
            background-color: #ADD8E6;
        }
        .container {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 2rem;
            text-align: center;
        }
        .title {
            color: #2c3e50;
            font-size: 3rem;
            margin-bottom: 2rem;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        .subtitle {
            color: #34495e;
            font-size: 1.5rem;
            margin-bottom: 3rem;
            max-width: 600px;
        }
        .buttons-container {
            display: flex;
            gap: 2rem;
            margin-bottom: 3rem;
            flex-wrap: wrap;
            justify-content: center;
        }
        .btn {
            padding: 1rem 2.5rem;
            border: none;
            border-radius: 50px;
            font-size: 1.2rem;
            cursor: pointer;
            transition: transform 0.3s, background-color 0.3s;
            text-decoration: none;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
        }
        .catalog-btn {
            background-color: #3498db;
            color: white;
        }
        .catalog-btn:hover {
            background-color: #2980b9;
            transform: translateY(-2px);
        }
        .offers-btn {
            background-color: #e74c3c;
            color: white;
        }
        .offers-btn:hover {
            background-color: #c0392b;
            transform: translateY(-2px);
        }
        .cart-btn {
            background-color: #2ecc71;
            color: white;
        }
        .cart-btn:hover {
            background-color: #27ae60;
            transform: translateY(-2px);
        }
        .images-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 2rem;
            max-width: 1200px;
            width: 100%;
        }
        .product-card {
            background-color: white;
            border-radius: 15px;
            padding: 1rem;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
            display: flex;
            flex-direction: column;
            position: relative;
        }
        .product-card:hover {
            transform: translateY(-5px);
        }
        .tech-image {
            width: 100%;
            height: 250px;
            object-fit: cover;
            border-radius: 10px;
            margin-bottom: 1rem;
            cursor: pointer;
            transition: opacity 0.3s;
        }
        .tech-image:hover {
            opacity: 0.8;
        }
        .discount-badge {
            position: absolute;
            top: -10px;
            right: -10px;
            background-color: #e74c3c;
            color: white;
            padding: 0.5rem;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            animation: pulse 2s infinite;
            z-index: 1;
        }
        .product-info {
            text-align: left;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }
        .product-title {
            font-size: 1.2rem;
            color: #2c3e50;
            margin-bottom: 0.5rem;
        }
        .product-description {
            color: #7f8c8d;
            font-size: 0.9rem;
            margin-bottom: 0.5rem;
        }
        .product-price {
            font-size: 1.4rem;
            color: #2ecc71;
            font-weight: bold;
            margin-bottom: 1rem;
        }
        .add-to-cart-btn {
            background-color: #3498db;
            color: white;
            padding: 0.8rem;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: background-color 0.3s;
            font-size: 1rem;
            width: 100%;
        }
        .add-to-cart-btn:hover {
            background-color: #2980b9;
        }
        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }
        .modal-content {
            background-color: white;
            padding: 2rem;
            border-radius: 15px;
            max-width: 600px;
            width: 90%;
            position: relative;
            max-height: 90vh;
            overflow-y: auto;
        }
        .close-modal {
            position: absolute;
            top: 10px;
            right: 10px;
            font-size: 1.5rem;
            cursor: pointer;
            background: none;
            border: none;
            color: #2c3e50;
        }
        .specs-list {
            list-style: none;
            text-align: left;
            margin: 1rem 0;
        }
        .specs-list li {
            margin-bottom: 0.5rem;
            padding-left: 1.5rem;
            position: relative;
        }
        .specs-list li::before {
            content: "•";
            color: #3498db;
            font-weight: bold;
            position: absolute;
            left: 0;
        }
        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        @media (max-width: 768px) {
            .title {
                font-size: 2rem;
            }
            .subtitle {
                font-size: 1.2rem;
            }
            .buttons-container {
                flex-direction: column;
                gap: 1rem;
            }
            .btn {
                width: 100%;
                text-align: center;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 class="title">Accesorios Tecnológicos Danstev</h1>
        <div class="flex items-center space-x-4">
            <a href="#" class="text-gray-600 hover:text-gray-800" id="userAccount">
                <i class="fas fa-user"></i>
            </a>
            <div class="relative">
                <a href="#" class="text-gray-600 hover:text-gray-800" id="cartIcon">
                    <i class="fas fa-shopping-cart"></i>
                    <span class="cart-badge" id="cartCount">0</span>
                </a>
            </div>
        </div>
        <p class="subtitle">Descubre nuestra exclusiva colección de accesorios para todos tus dispositivos</p>
        <p class="subtitle">Somos una empresa dedicada a la venta de accesorios y soporte tecnico</p>
        <div class="buttons-container">
            <a href="https://drive.google.com/file/d/1mV__4QwFVbg-AfwrQcvBVsmQmP5OcuD0/view?usp=sharing" class="btn catalog-btn">Ver Catálogo</a>
            <a href="https://drive.google.com/file/d/1T7FW3d4W3_1Mga67b1oFY2yGQ91RDDOj/view?usp=sharing" class="btn offers-btn">¡Ofertas!</a>
        </div>
        <div class="images-grid">
            <div class="product-card">
                <div class="discount-badge">-20%</div>
                <img src="https://http2.mlstatic.com/D_NQ_NP_695328-MLU76353991272_052024-O.webp" alt="Auriculares Gaming" class="tech-image" data-specs="Sonido envolvente 7.1 virtual|Micrófono con cancelación de ruido|Iluminación RGB personalizable|Almohadillas de espuma viscoelástica|Conexión USB|Peso: 350g|Compatible con PC y PS4|Garantía de 2 años">
                <div class="product-info">
                    <h3 class="product-title">Auriculares Gaming Pro</h3>
                    <p class="product-description">Auriculares gaming con sonido envolvente 7.1, micrófono retráctil y luz RGB</p>
                    <p class="product-price">$70.000</p>
                    <button class="add-to-cart" data-id="1" data-name="Auriculares Gaming Pro" data-price="70000">Agregar al Carrito</button>
                </div>
            </div>
            <div class="product-card">
                <img src="https://http2.mlstatic.com/D_NQ_NP_912908-MLU73832805668_012024-O.webp" alt="Power Bank" class="tech-image" data-specs="Capacidad: 20000mAh|Carga rápida 3.0|Dos puertos USB-A|Un puerto USB-C|Pantalla LED|Protección contra sobrecarga|Carcasa de aluminio|Peso: 380g">
                <div class="product-info">
                    <h3 class="product-title">Power Bank 20000mAh</h3>
                    <p class="product-description">Batería portátil de alta capacidad con carga rápida y dos puertos USB</p>
                    <p class="product-price">$50.000</p>
                    <button class="add-to-cart" data-id="2" data-name="Power Bank 20000mAh" data-price="50000">Agregar al Carrito</button>
                </div>
            </div>
            <div class="product-card">
                <div class="discount-badge">-30%</div>
                <img src="https://http2.mlstatic.com/D_NQ_NP_637791-MLU71846648318_092023-O.webp" alt="Mouse Gaming" class="tech-image" data-specs="Sensor óptico 16000 DPI|8 botones programables|Iluminación RGB|Memoria interna|Cable trenzado|Peso ajustable|Software personalizable|Garantía de 2 años">
                <div class="product-info">
                    <h3 class="product-title">Mouse Gaming RGB</h3>
                    <p class="product-description">Mouse gaming con sensor óptico de alta precisión y iluminación personalizable</p>
                    <p class="product-price">$40.000</p>
                    <button class="add-to-cart" data-id="3" data-name="Mouse Gaming RGB" data-price="40000">Agregar al Carrito</button>
                </div>
            </div>
            <div class="product-card">
                <img src="https://dobleclicknet.com/wp-content/uploads/2024/07/2.png" alt="Teclado Mecánico" class="tech-image" data-specs="Switches mecánicos Blue|105 teclas|Anti-ghosting completo|Retroiluminación RGB|Reposamuñecas magnético|Construcción en aluminio|Teclas macro programables|Puerto USB pasante">
                <div class="product-info">
                    <h3 class="product-title">Teclado Mecánico RGB</h3>
                    <p class="product-description">Teclado mecánico con switches Blue, retroiluminación RGB y reposamuñecas</p>
                    <p class="product-price">$80.000</p>
                    <button class="add-to-cart" data-id="4" data-name="Teclado mecanico RGB" data-price="80000">Agregar al Carrito</button>
                </div>
            </div>
            <div class="product-card">
                <div class="discount-badge">-15%</div>
                <img src="https://panamericana.vtexassets.com/arquivos/ids/479860/camara-web-havit-fhd-4k-8-mp-hv-nm07p-3-6939119034016.jpg?v=638107070854800000" alt="Webcam 4K" class="tech-image" data-specs="Resolución 4K Ultra HD|60 FPS|Micrófono dual|Enfoque automático|Campo visual 90°|Corrección de luz|Clip universal|Compatible con Windows y Mac">
                <div class="product-info">
                    <h3 class="product-title">Webcam 4K Pro</h3>
                    <p class="product-description">Webcam profesional 4K con micrófono dual y corrección de luz automática</p>
                    <p class="product-price">$60.000</p>
                    <button class="add-to-cart" data-id="5" data-name="Webcam 4K pro" data-price="60000">Agregar al Carrito</button>
                </div>
            </div>
            <div class="product-card">
                <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBxATEhUUExIVFhUXFxoVGBgXFxUYGhcVFxcXGBUWGhcYHSohGRslHRgXITEhJSkrLi4uFyAzODMsNygtLisBCgoKDQ0OFw8QFisdHSUtLTctKy0uLS0uLS0rKy0rKysrKystLS0tKy0tLSstLS0tKysrLS0tKy0tLy03LS0tK//AABEIAOEA4QMBIgACEQEDEQH/xAAcAAEAAQUBAQAAAAAAAAAAAAAAAwECBAUHBgj/xABBEAABAwIEAgcFBgQFBAMAAAABAAIRAyEEEjFRQWEFBiIycYGRE0KhsfAHI1JywfFigrLRFDNDU+FzksLSJGOi/8QAGAEBAQEBAQAAAAAAAAAAAAAAAAECBAP/xAAeEQEBAQEAAgMBAQAAAAAAAAAAARECAxIhMUFRFP/aAAwDAQACEQMRAD8A7axggWGiuyDYeiM0HgrkFuQbD0TINh6K5EFuQbD0TINh6K5EFuQbD0TINh6K5EFuQbD0TINh6K5EFuQbD0TINh6K5EFuQbD0TINh6K5EFuQbD0TINh6K5EFuQbD0TINh6K5EFuQbD0TINh6K5EFuQbD0TINh6K5EFuQbD0TINh6K5EFuQbD0TINh6K5EFuQbD0TINh6K5EGDlGw9EV0HZEGW3RVVG6KqAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgiREQSN0VVRuiqgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiIIkREEjdFVUboqoCIiAiIgIsPFdK4en/AJlekz8z2j5lajFdd+jmf64d+RrnfECEHo0XicR9pOFFmUqrvHK0fM/JanEfaZWP+Xh2D8zi75Qrg6Yi5O/rv0g/3mU/ys/95WnxnWLHOkOxNTydA9GwmDtz3gakDxstfien8HT7+IpDlnaT6BcMrVXv7znOPMk/P60VrQmDsWI69dHt0ql35WP+ZAC1eI+0rDjuUarvHK39SuaBv19fVlf7FXFe2xH2l1j3MOwfmc53yAWT0b9pQJivRgfipmY/lP8AdeJwFRrJD2Zhwkm3ob/XgpcXjKT2wKIGxEgjzJPopiO1dH4+lWYH0nh7TxHDkRqDyKyVwXovpStQfnpPLDx2I2cNCF0nq518o1oZXilU0n3HHxPdPI+qYPYoqAqqgIiICIiAiIghlVVsoguq12Mbme4NaBJJMAeZXmcZ9oWAYYa59Q/wNMceLoHBaz7Ww44eiATBeZbwectm+MTHOFy2nf69bcODvIhB07Efagz/AE8M4/neG6i2gPG3itTiftKxh7lOkwW1DnEA2mZAsRsvHBm9t+V4dHnDh4qT2W9hx5T2Xjw0Pmrg2+K66dJP1rlttGta247wkCeIWrxHSGIqHt1qrrx2nuNnXFphBSIueF/NvZcPQhVGHiRsCP8AsIj4KjEbTt/LHm39lJ7PX8oKzBRv/N/U0lW5bfyD+ohFQmnr4KRrIOsR+v7KUgSebgPh8k18yT5BURZOXMpkty+Z/dS6+fy+o+Ku8PLw3+fqggDOSuy/QUkfW6lp0XGYaTGwMDxI+rIMcfX19aq76+vrgp6OHzGMwHjInwgXP9llMwQj6+SDXhWPYtr/AIRvirThAeSYjTuao3sW0q4M8FiVaRCYrb9XOuWIwsNJ9pS/A43A/hdw8NF1HoLrBh8U2aT+0NWGzm+I25iy4dUYrKVd9Nwcxxa5twQSCDyKliPolFzfqz9o2lPFjkKrR/W0fMei6Jh67HtDmODmkSC0ggjkQsiRERAREQYyKqINV1v6D/xeGyDvtOdk6FwBEHxBIXGMVh3Nc4kEOaYeDYyDd3iLh3Ik7r6DbovE9fureYHE0R22iXge80e+B+Icdx4IOZ0CNNee4A/9DH8qybcfP+h0+RaeSxXNA7Q7vEfhNzA5EF0eMbTMwgiD4H+gn0ylaErDpPIHxMsePUBGE2nds+Ycwj1Vkk8yR65hP9TD6qR15P5iJ4iWvA+aKsYNP5PgciFtv5T8Hn9PgpXN1/m12FQGD5FX0aUzt2hf/qfXwVEbKJJsPfJ9AFO3o14Am1o8+KzWGNdL/NZAqXsJ8UGsdgTw5DwAVKeHh3aBI4iYt48N1s3OnWyhdlvN0iMWgS0OIbT4RnGYgcpEK6WFoDPaFxM5ey1voFIaZiYt5eipDCO3mMWAEaawmC6o0tc0OY1losZJ8RmPPVX+F1iNqupkloFzYlrXEeBI2RmJnU35fovTjmW5RmByjquVcOQTdZuNwrGNDg6ZGm3iur/NM+2Pdr2VpsosRqRH7cFZ7bkFe6uwzLZOgOYiPILm9ZJdbYVaiOCxH0ls6jGgCH5jxABtbfisfEUyNRr+yxM/RqajFsegesuJwbppP7J7zHXY7y4HmFBVCw69NZqu19V+uuGxkNn2db/bcdfyO9758l6ZfMD5BkSDwXveqX2lVqUU8VNWnoH/AOo0c/xj4+KyjsSLE6N6So4hgqUajXsPEcDsRqDyKy1BBlRVRBKzQKqozQKqDk3X/q4cNUNek2aDzDm8GOOrbaNPDY+S8jSERBJBFj/+YP8AEOwPOYuvoHGYVlVjqdRocxwLXA8QVwfpfDMwuLrYcPzsY8Akd5hLQ9hj8QDhyN/KwXteJnnPxDh6Bzlc13Dax8g9k+oHiochEiOEWkiHZw0gwAZBZ+6mBkyN5tzcw8OADlVXsaXHLaTa5ABljHXJsL3JW2yAGHEbWiNRGllpaLmiMwJaBcDXLkcPU5d1k4TFOD4sRfhrdtxtE6TdanyjNe2dAY/5VKcze3/JVBUP15q6mJXtz4bUvUi85VAcSdt/Tgs49HvAzaDf1WFiKjA42PiOX1CvfhvM2VJ1KvYwPtEFYzzBI2ken91PRxDQbDT4Rc/EgKEvLnHK2TP5oI5aQLKzPTb9r+rC76/RY1ZkXH1/Yc1n/wCDjvuDeWp8gFjlk2F/AH6j5rFsqrMLWdMASfDbYfqpzVmczjtEGfQ6KDDMbcmpljacx+tlFiQ3VrTlFiTNz5eVl6zz3nnGfX5VJvPBVc2OIJ5eSvrBzYzVA4fhDj84+p2ujKmZwFMBvi75+XKbLm662tI7jcH02Vr3zqVI5wDiHHOd2m3nb46LGqCwMi+gmT9ahZqoqxWI8/X15KzGY6nTEvcBtz8N9rTCUMSx4lptaxBBvMCDyafRRFr6crGqU4Wa/wCvr4rGqO+v0jdBl9X+nq+EqipSdH4mnuvbs4et+C7/ANB9KMxNBlZlg8abOBhzT4EFcN6B6q1sTUAMsB4avI3/AIRzK7n0J0VSwtFlGkIawRzJNyTzJuoMhERQSs0CqqN0XgPtX68YjoxtL2VNrva5hmPAti0efNB0BcNxIwZ6Y6SGKqNpsdTljz7rwaeUj4g8pXi8X1/6RxjiKuJqNbMBlJoJcTNrw0aawtV0i8h4MBx9mL1MlUjQSSZaTzg6pg930dVY8ANcx0E+zeCCO8C5mYgwxxaL8CpWNIEEaDKJmxa0jL2ohk0tYvsvHdW+lavtgx2eoHwIALi3gC1rRZu4Ahe8fRLs1u2BDgRJe0Nc0W4uaHG3EcwFoQVaetzAzc4vWE7XtCspuIdbeCBwk0pG0Qb+PFZFNwf2gZBMgjtmXOOnBwh/OOUKykwEt4js2nN2Zw/duAQSZJSCejULojW1he8W8rqZj8p/bS2o5rFw+Ee+cuVstuAbQWsJIH+0CQIJtAngVfRqsBOcGQeBDhEvIu07NJtMSNF1+Pzf1m862FfpEloaP3tpHr6rXVSRqCPHl2iPWylIL+62ItvyALtDx/7VZVpkO7Zne82ub8rAfJXyeTZkOecRAkWuY4bxcjxLjHkr3Unt7V/HQmL24yT8llMqxamy+km5mJgnhc6zGqrVpuN3vvwHOPQGduS5/ZpiNABOaTzaRrF3TxuY9VLRpOMlpyjYu4gRFv14q1lYABoaJPE8ZkjXkCSOCjxFCG3c2YkN1kcBbgTxiOcBWdCEvaMwcC502cHenidp4RoqudVNOZ7At3h4Abx4+QVWYiGwGNvbMRM6ATM3J3tEWsqVcK0Nk1G8TABI1HAcBtGuyxbaKMyhzfZguOzmjy428PiVI52Z33zi2NBEbWHmPGBraFqOkenKTWts0HgRMn8sTnN+80Ea3ErXtbjMSbAsZ+J0THJtxw45uULI2uJ6dp0AcrrHSQJnllknyB5gLVsdisSey32bD7zwJM6wy49ZHgtrger1KmcxHtH8XPJJ+K2ReBYX+Q81cGrwnV+k2S6XuIu5xJPqVEOg3SAx0Nvwu2dcsftuoOk65NTJVqF5nsYehIJHA1XTI8JAHNeipdTulMRR9oaTYtlw/tPZtcN6j4zVANrNPNQYeCFLtNpEPc2xfcsab2LxZxF+y023W86t9VnVDNJkmb1Xiw3A/sFuupf2eVaY9pjnsc7RtGlalTaNGjSfq5XRKVNrQA0AAWAAgAcgoMHoXolmHZlbcm7nHVx/QbBbBEUEKIiCVui8j9pnVI9I4YMaQKlN2dkxcxBF165uiqg+R8d0JicO9zagIc2xaReOMA/V1juqgOpANJHs8obmIzFrh2XZRJmJIESvqLrV1Vw+NZDxlqAdmoBccjuFxnHdUamErPbVbBsadRujokEjfUSPkqNl1V62YnD4TLS6Nw4riTmtRYQbtHswMxdwObL4ras6I6SqUn4vEvwznuIeG4aey2LmRYkQOJOsleV9q5hh/kRofrZbjojp2rRPYdY6tN2u8R+qCzE2OcDslzTUEmGE1KUvEaMIaZAgSb2MhhtWmeNPW1yMJAIGhA4CxWVVxdNz81MZZmWG4E95o/Ew7eSw2RTc1otTc4Bh0yEvoD2ZdwAFORa410uVJSIytkfgsddMNeBxk66fFVoVGZe0zMSLSct3NaSYFtKhBfEdoqzDm7ezlLMkjSw/w2UHXJobAuBi8Jh6cBo0AyA8Mp/+NmJgnLZpFpbutaL6WftZHQLujNlkTULQANB3bizhuFfhzSaDnkkGCDYW+7kj3ZLXW43hQtGlrw2RvIosB5d9+7d+VrRIEEi1oi2Zsm++auL923BNGWynUeQ5rcgga2iRmdYjUktBEHQ8VHReGvioC4yBYg8ogbQ8mTIvY8KZ3QYJjUtBgXL3gSeGVrBeRexCgqUrEW0yngP9tsz7oiqYOvAqCOS9wgDtXHdsHSZnh2ABwIzKatQyGSWu4kSeJvOkCMrZtMqNs3PnEEQYBvoSZNNob3h/EhYd/A8xImwuS7M4nkJCC/E44kZQABYQBreDHMmwGuxWhxXR2JqkZHtj3jHdg9kNBEQI7xBcDIkWWwqHyt6dmdNmtM7FzhcKH2haZFiPEmwuOdoAGsk95NRN0X1bo0jmdL3nVzpJJ8Tc+a2dWsxluOw15Tt5rRdN9OVBTJYMpA90B3aBuDcHLqMzbiCtV1YZi6pLcOxzn1DOZ2ZzG/lae1UcNzYRcpo9Jj+kGU25qrwxpsBxcdgNXnkLKnRPRHSHSBy0WOoUdC91nx46U/AS5ez6qfZgxjhWxjjVqm8EyfAkWaP4W+pXR6FBjGhrGhrRYACAPIKaPLdUuoODwQkND6mpe699wDqeZk+C9aiKAiIgIiIIUREErdFVUboqoCxOkujqVdhp1WhzT6g8CDqDzWWiDkfWrqnVw0uH3tD8UXbyeP8AyFvBePq0nNuySNtSPDdfRbgDYrn/AFq6h61cIADq6loD/wBPb8um0aIOW08aQZB0W7w+JZWYZFjAcOIIMhw2IIBB5LWY7AhxIILHgwZEXHBwPH4rU08RVw9QEi3HZwVHoGPNP7tx7TGk03AAZ2MYLhrSDIyiWsA5yLrK9oO1HDO3z+/zRl1P3Qs2DvKjxVFlelEwHCWuLQcpI4tcCCOBBUOHrZ3ODgRUuHg9qz31+Mkln3ojNDQDwmEVmmpBkaAuy7At9sGttF/uhZsHcFTSLmCcpII5sL3OgNuT9w2zYJm4KxKb2uIMSHwY17JLNI7zfvjYSwbqeg6cu5Ag3Mh/si4SJzCKj7DMNdEVkNgRFwJIO8ENLYbqYw7uy3e7VFUYCQDf3SdYygNcQBM3Ncw2WiLgKb2oNyLOjOLut2c0RM2fUsJFtW3KkNFrh2rl7QHO/PrcTmj2tQjXTvBBiMBIB0JAN41cQ+AJgw6owTdoyat0UVSmIOsb6mDMRPE0294kf5lnOWbUfqQSDJcTOhdZvER2qvAgn2ffMQtLiOkM7suHbncC2T3WMEh0PeIDRApAtETDpzaIi3FVCJmxk8YvN5PBubUxJFM9lyw6TX1LsGVn43ixHAge8bkxpJ90iFMcKxt6rhWcLf8A1tjQBts0X1EXJDRK9T1f6o4rFkPfNKl+Jw7Th/A3bmbeKajF6pdTW4tzr9hsB73DMTOjGjQWHynMutdDdC0MM3LSYBu7VzvE/por+h+iqWGpClSENF73LidXE8Ss5QEREBERAREQEREEKIiCVuiqqN0VUBERAREQee60dU6OLGbuVgLVANdg8e8PiFyPp7oath3GlXZGx1a4fia7j89131YfSnRlHEUzTqsDmn1B3B1B5hBwboeuDSby7PoYTpOgXFtRjg2owgtJEhwBDg1w2kWcLt1HFeyxn2Xuw7Kr8PXfU94UntbPOHN1McIvAXiK1ZBi4fpRoOSoCx+Vssdo4spsEjNOe9IQSah5tW5ZU7w1BzaEm49s1smTMEU+8THKAtJXqNcMrmtc3ZwBH/HksQUKY7pqs4dioY5WeD4qj2LjmMTd3ZGvaDi6+5gVqdxYQO0FrMX0wwHK0ueXkn2bLuktdBBbpHtieyfcHbEQtIMOw959Zw2NQAbe60HSBrwGy3HQfRNatmbhMOXfiLYGmgdUebnkSi6trOfUE13wDP3NMxYkkh9RumujL2EuKyujcLXxLhRw1Kw91gysYNydB4m55r03Vn7Nq9SH40+yb/tMcHOPJzxYeU/qundHdH0aDBTpMaxo4AfEnUnmVEeW6sdQaNCKleK1XW/caeTT3jzPoF7NEQEREBERAREQEREBERBCiIglboqqjdFVAREQEREBERAXPOvXUE1i6vhYFQ3fTNg88XNOgduDY8uPQ0QfMmIwldtX2TqVQVZgUy05ieAA4rqfQH2VUBTDsVUqPqODSWtIa2mY7TWkCXXtJ2XR4Cqg8phPs76MYZ9iX/ne9w9Jgr02Hw7KbQ1jWsaNGtAAHgApUQEREBERAREQEREBERAREQEREEKIqoJG6Kqo3RVQEREBERAREQEREBERAREQEREBERAREQEREBERAREQEREESIiC9mg8Fcraeg8FcgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiIMTOUVsogtZoFciICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiAiIgIiICIiDFREQf//Z" alt="Base Refrigerante" class="tech-image" data-specs="6 ventiladores silenciosos|Panel de control LCD|7 niveles de velocidad|RGB personalizable|Compatible hasta 17'|2 puertos USB|Ajuste de altura|Diseño metálico">
                <div class="product-info">
                    <h3 class="product-title">Base Refrigerante Gaming</h3>
                    <p class="product-description">Base refrigerante para laptop con 6 ventiladores y panel LCD</p>
                    <p class="product-price">$65.000</p>
                    <button class="add-to-cart" data-id="6" data-name="Base Refrigerante Gaming" data-price="65000">Agregar al Carrito</button>
                </div>
            </div>
            <div class="product-card">
                <div class="discount-badge">-25%</div>
                <img src="https://www.steren.com.co/media/catalog/product/cache/0236bbabe616ddcff749ccbc14f38bf2/image/2157701cc/microfono-usb-c-de-solapa-para-celular.jpg" alt="Micrófono USB" class="tech-image" data-specs="Patrón cardioide|Resolución 24-bit/96kHz|Monitoreo sin latencia|Control de ganancia|Soporte antivibración|Filtro pop incluido|Base de escritorio|Conector USB-C">
                <div class="product-info">
                    <h3 class="product-title">Micrófono USB Profesional</h3>
                    <p class="product-description">Micrófono condensador USB para streaming y grabación profesional</p>
                    <p class="product-price">$30.000</p>
                    <button class="add-to-cart" data-id="7" data-name="Micrófono USB Profesional" data-price="30000">Agregar al Carrito</button>
                </div>
            </div>
            <div class="product-card">
                <img src="https://lexatecnologia.com/rails/active_storage/representations/proxy/eyJfcmFpbHMiOnsiZGF0YSI6NzE5MDUsInB1ciI6ImJsb2JfaWQifX0=--0d50ff9267bda6a9ebbe0d6bad3c6768ca786a56/eyJfcmFpbHMiOnsiZGF0YSI6eyJmb3JtYXQiOiJ3ZWJwIiwicmVzaXplX3RvX2ZpdCI6WzYwMCw2MDBdfSwicHVyIjoidmFyaWF0aW9uIn19--f071e30ecad735fd2ab55c9d9f5412fe02d64321/1-D-CAP-VIDEO.png?locale=es" alt="Capturadora" class="tech-image" data-specs="Captura 4K a 30fps|Pass-through 4K a 60fps|Audio sin latencia|HDMI 2.0|USB 3.0|Compatible con PS5/Xbox|Software incluido|Plug and Play">
                <div class="product-info">
                    <h3 class="product-title">Capturadora de Video 4K</h3>
                    <p class="product-description">Capturadora de video para gaming y streaming en 4K</p>
                    <p class="product-price">$20.000</p>
                    <button class="add-to-cart" data-id="8" data-name="capturadora de video gaming" data-price="20000">Agregar al Carrito</button>
                </div>
            </div>
            <div class="product-card">
                <img src="https://www.alkosto.com/medias/711719504313-001-750Wx750H?context=bWFzdGVyfGltYWdlc3wyNzMwNXxpbWFnZS9qcGVnfGFXMWhaMlZ6TDJneU1pOW9aVEF2T0Rnek16UTNPREl6TURBME5pNXFjR2N8MTIwNjhkYWUwNmUwY2JmYmFhZjc0ZGI4ZGEwODgwZGI2ODdkZTBlMWQzMDVmNDg2MTMxYzJjMjVjOGIxYWYwMQ" alt="Controles gamer" class="tech-image" data-specs="Control de precisión: la sensación, la forma y la sensibilidad de las palancas analógicas y los botones de activación del Dualshock 4 se han mejorado para ofrecer a los jugadores un control absoluto de todos los juegos de PlayStation 4.">
                <div class="product-info">
                    <h3 class="product-title">Control de videojuegos</h3>
                    <p class="product-description">control de videojuegos gamming</p>
                    <p class="product-price">$55.000</p>
                    <button class="add-to-cart" data-id="9" data-name="control de video juegos gamming" data-price="55000">Agregar al Carrito</button>
                </div>
            </div>
                         <!-- Cart Modal -->
    <div id="cartModal" class="modal">
        <div class="modal-content">
            <div class="flex justify-between items-center mb-4">
                <h2 class="text-2xl font-bold">Carrito de Compras</h2>
                <button id="closeCart" class="text-gray-600 hover:text-gray-800">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <div id="cartItems" class="space-y-4 mb-4">
                <!-- Cart items will be inserted here -->
            </div>
            <div class="border-t pt-4">
                <div class="flex justify-between items-center mb-4">
                    <span class="text-xl font-bold">Total:</span>
                    <span id="cartTotal" class="text-xl font-bold">$0</span>
                </div>
                <button id="checkout" class="w-full bg-green-600 text-white py-2 rounded hover:bg-green-700">
                    Proceder al Pago
                </button>
            </div>
        </div>
    </div>
    <!-- Login Modal -->
    <div id="loginModal" class="modal">
        <div class="modal-content">
            <div class="flex justify-between items-center mb-4">
                <h2 class="text-2xl font-bold">Iniciar Sesión</h2>
                <button id="closeLogin" class="text-gray-600 hover:text-gray-800">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            <form id="loginForm" class="space-y-4">
                <div>
                    <label class="block text-gray-700 mb-2">Email</label>
                    <input type="email" class="w-full p-2 border rounded" required>
                </div>
                <div>
                    <label class="block text-gray-700 mb-2">Contraseña</label>
                    <input type="password" class="w-full p-2 border rounded" required>
                </div>
                <button type="submit" class="w-full bg-blue-600 text-white py-2 rounded hover:bg-blue-700">
                    Iniciar Sesión
                </button>
            </form>
        </div>
    </div>
    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-12">
        <div class="container mx-auto px-6">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div>
                    <h3 class="text-xl font-bold mb-4">Contacto</h3>
                    <p class="mb-2">Teléfono: +57 3203435413</p>
                    <p>Email: monroydaniel05@gmail.com</p>
                </div>
                <div>
                    <h3 class="text-xl font-bold mb-4">Enlaces Rápidos</h3>
                    <ul class="space-y-2">
                        <li><a href="#catalogo" class="hover:text-gray-300">Catálogo</a></li>
                        <li><a href="#ofertas" class="hover:text-gray-300">Ofertas</a></li>
                        <li><a href="#" class="hover:text-gray-300">Soporte Técnico</a></li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-xl font-bold mb-4">Síguenos</h3>
                    <div class="flex space-x-4">
                        <a href="#" class="hover:text-gray-300"><i class="fab fa-facebook"></i></a>
                        <a href="#" class="hover:text-gray-300"><i class="fab fa-instagram"></i></a>
                        <a href="#" class="hover:text-gray-300"><i class="fab fa-twitter"></i></a>
                    </div>
                </div>
            </div>
        </div>
    </footer>
    <script>
        // Cart functionality
        let cart = [];
        let cartTotal = 0;
        function updateCartUI() {
            const cartCount = document.getElementById('cartCount');
            const cartItems = document.getElementById('cartItems');
            const cartTotalElement = document.getElementById('cartTotal');
                        cartCount.textContent = cart.length;
            cartItems.innerHTML = '';
            cartTotal = 0;
            cart.forEach(item => {
                cartTotal += item.price * item.quantity;
                const itemElement = document.createElement('div');
                itemElement.className = 'flex justify-between items-center';
                itemElement.innerHTML = `
                    <div>
                        <h4 class="font-bold">${item.name}</h4>
                        <p>Cantidad: ${item.quantity}</p>
                    </div>
                    <div class="text-right">
                        <p class="font-bold">$${item.price.toLocaleString()}</p>
                        <button class="text-red-600 hover:text-red-800" onclick="removeFromCart(${item.id})">
                            Eliminar
                        </button>
                    </div>
                `;
                cartItems.appendChild(itemElement);
            });
            cartTotalElement.textContent = `$${cartTotal.toLocaleString()}`;
        }
        function addToCart(id, name, price) {
            const existingItem = cart.find(item => item.id === id);
            if (existingItem) {
                existingItem.quantity += 1;
            } else {
                cart.push({ id, name, price, quantity: 1 });
            }
            updateCartUI();
        }
        function removeFromCart(id) {
            cart = cart.filter(item => item.id !== id);
            updateCartUI();
        }
        // Modal functionality
        const cartModal = document.getElementById('cartModal');
        const loginModal = document.getElementById('loginModal');
        const cartIcon = document.getElementById('cartIcon');
        const userAccount = document.getElementById('userAccount');
        const closeCart = document.getElementById('closeCart');
        const closeLogin = document.getElementById('closeLogin');
        cartIcon.addEventListener('click', () => {
            cartModal.style.display = 'block';
        });
        userAccount.addEventListener('click', () => {
            loginModal.style.display = 'block';
        });
        closeCart.addEventListener('click', () => {
            cartModal.style.display = 'none';
        });
        closeLogin.addEventListener('click', () => {
            loginModal.style.display = 'none';
        });
        // Add to cart buttons
        document.querySelectorAll('.add-to-cart').forEach(button => {
            button.addEventListener('click', () => {
                const { id, name, price } = button.dataset;
                addToCart(parseInt(id), name, parseInt(price));
            });
        });
        // Checkout functionality
        document.getElementById('checkout').addEventListener('click', () => {
            if (cart.length === 0) {
                alert('El carrito está vacío');
                return;
            }
            // Here you would typically integrate with a payment gateway
            alert('Redirigiendo al sistema de pago...');
        });
        // Login form submission
        document.getElementById('loginForm').addEventListener('submit', (e) => {
            e.preventDefault();
            // Here you would typically handle login authentication
            alert('Funcionalidad de login en desarrollo');
            loginModal.style.display = 'none';
        });
        // Close modals when clicking outside
        window.addEventListener('click', (e) => {
            if (e.target === cartModal) {
                cartModal.style.display = 'none';
            }
            if (e.target === loginModal) {
                loginModal.style.display = 'none';
            }
        });
    </script>
    </div>
</body>
</html>
