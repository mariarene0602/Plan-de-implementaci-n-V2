Dale, acá tenés las dependencias y entidades bien claras, sin vueltas:

---

## Dependencias (pubspec.yaml)

```yaml
dependencies:
  flutter:
    sdk: flutter
  
  # Firebase (sin analytics)
  firebase_core: ^2.24.2
  firebase_auth: ^4.15.3
  cloud_firestore: ^4.13.6
  
  # Estado
  provider: ^6.1.1
  
  # UI
  google_fonts: ^6.1.0
  font_awesome_flutter: ^10.6.0
  intl: ^0.19.0
  
  # Utilidades
  uuid: ^4.2.2
  image_picker: ^1.0.4
  cached_network_image: ^3.3.0
  fl_chart: ^0.66.0
```

---

## Entidades (Modelos)

### User (colección: users)

| Campo | Tipo | Descripción |
|-------|------|-------------|
| uid | String | ID de Firebase Auth |
| email | String | Correo electrónico |
| name | String | Nombre del dueño |
| createdAt | Timestamp | Fecha de registro |
| totalTrainings | int | Contador de sesiones |

### Dog (colección: dogs)

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | String | ID único |
| ownerId | String | uid del dueño |
| name | String | Nombre del perro |
| breed | String | Raza |
| age | int | Edad en años |
| photoUrl | String | Foto (opcional) |
| isActive | bool | Activo o archivado |
| registeredAt | Timestamp | Fecha de registro |

### TrainingSession (colección: sessions)

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | String | ID único |
| dogId | String | ID del perro |
| userId | String | uid del dueño |
| exerciseName | String | Nombre del ejercicio |
| score | int | 1 a 5 |
| date | Timestamp | Fecha de la sesión |
| observations | String | Notas (opcional) |
| durationMinutes | int | Duración (opcional) |

### ExerciseCatalog (colección: exercises_catalog) - Datos maestros

| Campo | Tipo | Descripción |
|-------|------|-------------|
| id | String | ID único |
| name | String | Nombre del ejercicio |
| description | String | Instrucciones |
| category | String | Básico, intermedio, avanzado |
| tips | String | Consejos útiles |

---

## Relaciones entre tablas

```
users (1) ──────< (N) dogs
users (1) ──────< (N) sessions
dogs (1) ───────< (N) sessions
```

- Un usuario tiene muchos perros
- Un usuario tiene muchas sesiones
- Un perro tiene muchas sesiones
- Cada sesión pertenece a un usuario Y a un perro

---

