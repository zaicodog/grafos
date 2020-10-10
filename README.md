# Proyecto-N-1-Grafos
Área de trabajo Proyecto Unidad N°1 Grafos y Lenguajes Formales


Importante arrastrar carpeta al editor, ya sea Atom o Visual Studio

-. Instalar extension Live Server
-. Segundo click y apretar "Runserver" para iniciar el servidor


<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css" integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk" crossorigin="anonymous">
    <!--Conexion Css -->
    <link rel="stylesheet" href="/css/index.css">
    <link rel="stylesheet" href="/css/grafos.css">
    <!--Font awesome-->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css">
    <!-- Google fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Oswald:wght@500&family=Roboto:wght@300;500&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/normalize.css@8.0.1/normalize.min.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/glider-js@1.7.3/glider.min.css">

    <!-- Libreria vis -->
    <link href="/dist/vis-network.min.css" rel="stylesheet" type="text/css" />
    <link type="text/css" rel="stylesheet" href="css/bootstrap.min.css">

    <link rel="icon" href="/img/Grafos.png">




    <title>Grafos a utilizar</title>
</head>


<body>

    <!-- Header-->

    <nav class="navbar navbar-expand-lg navbar-light bg-dark sticky-top p-3">
        <div class="container">
            <a class="navbar-brand" href="/html/index.html" style="color: #CDA434;">Grafos y Lenguajes Formales</a>
            <button class="navbar-toggler border-white" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <ion-icon name="menu-outline"></ion-icon>
            </button>

            <div class="collapse navbar-collapse" id="navbarSupportedContent">

                <ul class="navbar-nav ml-auto">
                    <li class="nav-item px-2">
                        <a class="nav-link" href="/html/index.html" style="text-align: center;">Inicio </a>
                    </li>
                    <li class="nav-item px-2">
                        <a class="nav-link" href="/html/nosotros.html" style="text-align: center;">Nosotros </a>
                    </li>

                </ul>
            </div>
        </div>
    </nav>


    <section id="grafos">
        <div class="container border border-dark mt-5 py-2 my-5">
            <h1 class="mx-5 text-center">Area de Trabajo</h1>
            <h1 class="dividerg mx-5"></h1>
            <div class="row d-flex">
                <div class="container mx-5">
                    <p class="text-center">En esta área podrás ingresar grafos con sus distintas caracteristicas, por ejemplo puedes elegir tu tipo de grafo , ingresar vertices, aristas, para finalmente mediante un analisis, poder obtener:
                    </p>
                    <div class="row justify-content-center">
                        <p>
                            <em class="fas fa-check-circle"></em> Matriz de adyacencia<br>
                            <em class="fas fa-check-circle"></em> Matriz de Caminos <br>
                            <em class="fas fa-check-circle"></em> Grafo Euleriano o Hamiltoniano <br>
                            <em class="fas fa-check-circle"></em> Camino más rapido<br>
                        </p>
                    </div>
                </div>
            </div>

            <h1 class="dividerg my-2"></h1>

            <div class="container">
                <h3 class="text-center">Instrucciones previas.</h3>
                <div class="row pt-3 justify-content-center">
                    <div class="col-md-6 mx-5">
                        <p><strong>1.</strong> Elige el tipo de grafo que ingresaras:</p>
                        <select class="form-control" id="tipoGrafo">
                        <option value="Simple">Grafo Simple</option>
                        <option value="Dirigido">Grafo Dirigido</option>
                        </select>

                    </div>

                    <div class="col-md-6">
                        <div class="row d-flex justify-content-center my-2">
                            <a onclick="draw()" id="btnComenzar" class="btn btn-outline-light px-2" style="text-align: center; max-width: 850px;">Ingresa un Grafo</a>
                            <select id="locale" style="display: none;"><option value="es">es</option></select>
                        </div>
                    </div>



                    <div class="col-md-6 mx-5" id="">
                        <p><strong>2.</strong>Comienza a ingresar tus grafos:</p>
                        <div class="col-12 my-2  shadow" id="resultado"></div>


                        <div id="node-popUp">
                            <span id="node-operation">Vértices</span>
                            <table style="margin:auto;">
                                <caption></caption>
                                <tr>
                                    <th id="th-id">id</th>
                                    <td><input id="node-id" class="form-control" placeholder="Ingresa un ID" /></td>
                                </tr>
                                <tr style="display: none;">
                                    <th id="th-nombre ">Nombre</th>
                                    <td><input id="node-label" class="form-control" placeholder="Nombre" /></td>
                                </tr>
                            </table>
                            <input type="button" class="btn btn-outline-light" value="Guardar" id="node-saveButton" />
                            <input type="button" class="btn btn-outline-light" value="Cancelar" id="node-cancelButton" />
                        </div>


                        <div id="edge-popUp">
                            <span id="edge-operation">Aristas</span>
                            <br>
                            <table style="margin:center;">
                                <caption></caption>
                                <tr>
                                    <td><input type="number" id="edge-label" class="form-control" min="0 " placeholder="Ingresa el peso del grafo " /></td>
                                </tr>
                            </table>

                            <input type="button" class="btn btn-outline-light" value="Guardar" id="edge-saveButton" />
                            <input type="button" class="btn btn-outline-light" value="Cancelar" id="edge-cancelButton" />
                        </div>
                    </div>

                    <!--Aca estamos haciendo las pruebas para mostrar la matriz-->
                    <div class="col-md-12">
                        <h3 class="text-center mt-4">Analisis de resultados</h3>
                        <h1 class="dividerg"></h1>
                        <div class="row">
                            <div class="col-4">
                                <h1>Matriz de Adyacencia</h1>
                                <a onclick="mostrarAdya()" class="btn btn-outline-light px-2">Mostrar Matriz</a>
                                <div id="matrizAdy"></div>
                            </div>
                            <!--<div class="row">
                                <button onclick="mostrarAdya()" class="btn btn-danger">Mostrar la matriz</button>
                                <div class="col d-flex">
                                    <div id="matrizAdy"></div>
                                    <h1>Acaaaa</h1>
                                </div>-->
                        </div>
                    </div>
                </div>

                <!--Aca termina -->
            </div>


        </div>
        </div>

        </div>

    </section>


    <!--Seccion footer-->

    <section id="footer">
        <nav class="container-fluid p-2">
            <div class="container">
                <div class="content-center">
                    <div class="row my-1">
                        <div class="col d-flex justify-content-center">
                            <a href="#" class="text-white">
                                <em class="fab fa-github"></em>
                            </a>
                        </div>
                    </div>
                    <h1 class="divider mx-5"></h1>
                    <h4 class="text-center"> Universidad Tecnológica Metropolitana | Desarrollado por: Grupo 5</h4>
                </div>
            </div>
        </nav>
    </section>





</body>


<!-- Optional JavaScript -->
<!-- jQuery first, then Popper.js, then Bootstrap JS -->
<script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/js/bootstrap.min.js" integrity="sha384-OgVRvuATP1z7JjHLkuOU7Xw704+h835Lr+6QL9UvYjZE3Ipu6Tp75j7Bh/kR0JKI" crossorigin="anonymous"></script>
<script src="https://unpkg.com/ionicons@5.1.2/dist/ionicons.js"></script>
<script src="https://kit.fontawesome.com/c8152ea011.js" crossorigin="anonymous"></script>

<script type="text/javascript" src="/js/grafosDraw.js"></script>
<script type="text/javascript" src="/dist/vis.js"></script>


</html>
</embrac.ce