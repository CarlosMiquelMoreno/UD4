## Minirreto 1: coloca cada servicio en su zona
# Zonas disponibles

1. Tabla de ubicación. Una fila por servicio:

| Zona | Confianza | Idea |
| ---- | --------- | ---- |
| Internet | No confiable | Cualquiera, sin control | 
| DMZ | Semiconfiable | Servicios expuestos a Internet, aislados de la LAN |
| LAN | Confiable | Usuarios y equipos propios |
| Zona crítica | Restringida | Activos de alto valor con pocos accessos |

| Servicios | Zona | Justificacion (una frase) |
| --------- | ---- | ------------------------- |
| Web corporativa pública | DMZ | Accesible desde internet pero aislada de la LAN. |
| Servidor de correo | DMZ | Recibe trafico que puede ser no confiable entonces lo ponemos en DMZ. |
| Pasarela VPN | DMZ | Necesita escuchar las peticiones para autenticar usuarios remotos. |
| Proxy (saliente e inverso) | DMZ | Filtro intermediario, recibe peticiones hacia servicios internos. |
| HMI de planta y carpeta de planos | Zona crítica | Archivos muy importantes de la empresa. |
| Autoridad de certificación (srv-ca) | Zona crítica | La propiedad certificadora, si es atacada puede llegar a ser muy prejudicial. |
| Servidor de copias de seguridad | Zona crítica | Si algo muy malo paso, es el cinturon de seguridad. |
| Portátiles de ingenieros y operarios | LAN | Dispositivos con los que se comunican los empleados. |
| Wi-Fi de invitados | Zona propia | Esta en mi infraestructura, les doy salida a internet pero nada mas. |
| Servidor de registros y monitorización | LAN | Tienen todo lo que pasa en la red. |

2. Tabla de flujos. Qué conexiones se permiten y cuáles no entre zonas:

| Origen -> Destino | ¿Permitido? | Ejemplo concreto |
| ----------------- | ----------- | ---------------- |
| Internet -> DMZ | Servicios Publicados | 80 y 443 a la web |
| Internet -> LAN | No | Nada |
| DMZ -> LAN | Casi imposible, muy pocas cosas | VPN -> srv-hmi | 
| LAN -> DMZ | Si | Administrar por SSH | 
| LAN -> Internet | Si | Navegación de usuarios |

3. Un diagrama de la red. Puedes dibujarlo con el bloque de Mermaid de abajo (GitHub lo muestra solo) o subir una imagen.

<img width="1152" height="637" alt="image" src="https://github.com/user-attachments/assets/10c7c884-9fcd-4733-a287-a81da0a29cd0" />

4. Una pregunta de reflexión (3 o 4 líneas): si cae el servidor web, ¿qué puede hacer el atacante en tu diseño y qué se lo impide?

