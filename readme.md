Trabajo práctico de Digital House donde se trabaja con modelos, se realizan consultas y un CRUD con sequelize, en esta oportunidad con relaciones entre bases de datos

descripcion: El objetivo será crear un CRUD incluyendo las relaciones entre las distintas tablas

    desafio 1:
        en los siguientes modelos(Movie,Genre,Actor) definir las siguientes relaciones segun corresponda:
            ● Una película tiene un género.
            ● Un género tiene muchas películas.
            ● Una película tiene muchos actores.
            ● Un actor tiene muchas películas.
    
    desafio 2:
        -CRUD
            -/movies/add(GET)
                -Mostrar el formulario de creacion de una pelicula
                -Agregar en la vista de detalle de pelicula, un boton de agregar que envie a esta url y un boton de listado de peliculas que conduzca a "/movies"
                -El formulario de creacion debe contar con un select que permita elegir el genero de la pelicula
                -Desde el controlador se le debe enviar la vista los generos de peliculas
            -/movies/create(POST)
                -Utilizara la conexion a la base de datos y el modelo de Pelicula ya creado. usar la funcion create de sequelize y luego redirigir al listado de peliculas
                -Validar con express-validator
            -/movies/edit/:id (GET)
                -En movieDetail agregar boton "modificar" que envie a esta url
                - el formulario debe contar con un select para elegir el genero de la pelicula, por defecto figurará el genero actual de la pelicula
                - el controlador debera utilizar sequelize mediante el id y el metodo findByPk para enviar los datos de los peliculas y cargarlos mediante los atributos value de cada input
            -/movies/update/:id (POST) ---> idealmente PUT
                - esta ruta recibe informacion del formulario, recuperando los datos mediante req.body, usando la conexion y el modelo Movie.
                -mediante el metodo update, se modifica la informacion de la base de datos y se redirige a al listado de peliculas
                - validacion por express validator
                -utilizar el paquete necesario para que el metodo responda por PUT
            -/movies/delete/:id (GET)
                - en moviesDetail se agrega un boton que lleva a esta ruta
                - el controlador recupera la id mediante req.params
                - el controlador debe devolver a la vista el nombre de la pelicula
            -/movies/delete/:id (DELETE)
                - se debe llamar a su misma ruta esta vez por DELETE
                - usar la conexion a base de datos y el modelo Movie
                - eliminarlo mediante el metodo destroy y redirigir al listado de peliculas