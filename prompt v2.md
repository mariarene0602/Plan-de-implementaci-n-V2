Necesito desarrollar una app en Flutter llamada Canis Academia para gestión de entrenamiento canino, multiplataforma (Android, iOS, Web, Windows). Backend Firebase con Auth (solo email/contraseña) y Firestore, cero analíticas, nada de rastreo. Estado con Provider. Colores: primario #2C3E50, acento #F39C12, fondo #F4F7F6. Entidades: User (uid, email, name), Dog (id, ownerId, name, breed, age, photoUrl opcional), TrainingSession (id, dogId, userId, exerciseName, score 1-5, date, observations).

Quiero que generes el código completo, archivo por archivo, para tener la app funcionando. Incluí:

pubspec.yaml con todas las dependencias necesarias (sin analytics)

main.dart con inicialización de Firebase

Modelos con toFirestore y fromFirestore

AuthProvider con login, registro, logout y manejo de errores claros

DogProvider con CRUD y stream en tiempo real

TrainingProvider con carga de sesiones, promedio de score, y filtros por perro

Pantalla de login y registro (validación básica)

Dashboard principal que muestre el perro seleccionado, score promedio, últimas sesiones

Selector de perros (switch entre perros del usuario)

Pantalla para registrar nueva sesión: seleccionar ejercicio de lista, puntuar 1-5, agregar nota

Pantalla de historial de sesiones por perro

Navegación adaptativa: BottomNav en móvil, Drawer en desktop/web

Reglas de seguridad de Firestore (solo dueño puede leer/escribir sus datos)

Script seed_data.dart dentro de lib/bin para cargar ejercicios iniciales (sentado, quieto, junto, venir, echado)
