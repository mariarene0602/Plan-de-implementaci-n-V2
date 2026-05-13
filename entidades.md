Entidades (Modelos)
User (colección: users)
Campo	Tipo	Descripción
uid	String	ID de Firebase Auth
email	String	Correo electrónico
name	String	Nombre del dueño
createdAt	Timestamp	Fecha de registro
totalTrainings	int	Contador de sesiones
Dog (colección: dogs)
Campo	Tipo	Descripción
id	String	ID único
ownerId	String	uid del dueño
name	String	Nombre del perro
breed	String	Raza
age	int	Edad en años
photoUrl	String	Foto (opcional)
isActive	bool	Activo o archivado
registeredAt	Timestamp	Fecha de registro
TrainingSession (colección: sessions)
Campo	Tipo	Descripción
id	String	ID único
dogId	String	ID del perro
userId	String	uid del dueño
exerciseName	String	Nombre del ejercicio
score	int	1 a 5
date	Timestamp	Fecha de la sesión
observations	String	Notas (opcional)
durationMinutes	int	Duración (opcional)
ExerciseCatalog (colección: exercises_catalog) - Datos maestros
Campo	Tipo	Descripción
id	String	ID único
name	String	Nombre del ejercicio
description	String	Instrucciones
category	String	Básico, intermedio, avanzado
tips	String	Consejos útiles
Relaciones entre tablas
text
users (1) ──────< (N) dogs
users (1) ──────< (N) sessions
dogs (1) ───────< (N) sessions
Un usuario tiene muchos perros

Un usuario tiene muchas sesiones

Un perro tiene muchas sesiones

Cada sesión pertenece a un usuario Y a un perro

