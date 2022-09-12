Docs : 
¿ Qué es ?
MaxTweet es un proyecto basado en Twitter creado en React usando Next js, en el cual podemos crearnos un usuario para  enviar tweets, likearlos,retweetearlos , guardarlos y comentarlos.
 Luego los tweets con los que hayamos interactuado o emitido , apareceran en nuestro perfil en sus respectivas escenas.
También se puede seguir y dejar de seguir otros usuarios.
Al seguir usuarios nos suscribimos su contenido  a nuestro feed, es decir , cada vez que el usuario seguido emita un tweet , este aparecera en nuestro feed , en la escena Home.

Escenas :
/profile 
En esta escena tenemos acceso a nuestro perfil de usuario , en el cual podremos ver nuestro tweets , likes , saves y replies. También desde aqui podremos eliminar nuestros tweets.

/profile/[userId]
En esta escena podremos ver el perfil de los demas usuarios de la app. Tendremos acceso a todo lo antes mencionado excepto por la opción de  eliminar tweets.

/edit-profile
Escena en las cual se nos permite modificar nuestros datos de usuario. Luego de el login se nos  redirijira a esta página para que elijamos una foto de perfil y una de portada.

/home
Escena principal en la cual se muestra el feed del usuario , las sugerencias de seguimiento y la posibilidad de leer algunas bromas.

/jokes
Divertite leyendo algunos chistes! Ojo con los de Chuck Norris que son un poco elevados de tono.

/bookmarks
En esta escena podremos inspeccionar los tweets que hayamos guardado.

/explore 
En esta escena se producen las busquedas. Estas pueden ser filtradas por 5 formas de busqueda. La primera es buscar simplemente desde la barra de busqueda y se nos devolveran usuarios que coincidan con los caracteres ingresados.
La segunda es filtrar por "Top" , esto filtrara los resultados por usuario con mayor cantidad de followers/seguidos.
La tercer opción es "Latest" lo que filtrara los resultados por orden de emisión , es decir, nos devolvera los tweets mas recientes.
La cuarta opción es "People" , esta nos devolvera usuarios aleatorios.
La ultima opción es "Media", esta opción nos devolvera los tweets que posean algun archivo media en ellos. 

/login
Escena para realizar el proceso de autorización.

Backend : 
Para el backend utilice las API routes de Next js  separando el proyecto en diferentes carpetas como controllers,models,lib,pages. Hice uso de librerias como JWT para el proceso de autorización , uso de middleware para comprobar autorización de parte del usuario.
Utilice Firestore como base de datos junto a Firebase Storage para almacenar las imagenes de los usuarios.

API routes : 
/auth
Contiene los endpoints relacionados a la identificación del usuario contra la base de datos

/auth/token
Endpoint que recibe el código obtenido del endpoint /auth y chequea en la base de datos si es correcto.

/tweet
Contiene endpoints relacionados a la creación , actualización , obtención y borrado de tweets.

/tweet/all
Contiene el endpoint para obtener todos los tweets.

/tweet/get/latest
Contiene endpoint para obtener los tweets mas recientes.

/tweet/get/media
Contiene endpoint para obtener los tweets que tengan un archivo media.

/tweet/comments
Contiene endpoint para crear nuevo comentario.

/tweet/comments/likes
Contiene endpoints para likear o deslikear comentarios.

/tweet/actions
acción de tweet = like,retweet,save,comment.

Contiene los endpoints que se encargan  de agregar (POST) una acción de tweet  o por el contrario remover acción de tweet.

/user
Contiene POST y DELETE para seguir o dejar de seguir usuario , por el otro lado también contiene PATCH para actualizar credenciales de usuario y GET para obtener el documento del usuario  de la base de datos.

/user/all
Contiene endpoint para leer todos los usuarios.

/user/suggestFollow
Contiene endpoint para recibir usuarios de sugerencia en la escena Home.

/profile/[userId]
Obtiene el perfil de un usuario mediante su userId.

/user/get/random
Obtiene diez usuarios aleatorios de la base  de datos.

/user/get/top
Obtiene los usuarios mas seguidos de la base de datos.

/user/feed
Obtiene el feed del usuario.
