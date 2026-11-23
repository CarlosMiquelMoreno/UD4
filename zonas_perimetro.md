## Minirreto 1: coloca cada servicio en su zona
# Zonas disponibles
| Zona | Confianza | Idea |
| ---- | --------- | ---- |
| Internet | No confiable | Cualquiera, sin control | 
| DMZ | Semiconfiable | Servicios expuestos a Internet, aislados de la LAN |
| LAN | Confiable | Usuarios y equipos propios |
| Zona crítica | Restringida | Activos de alto valor con pocos accessos |

| Servicios | Zona | Justificacion (una frase) |
| --------- | ---- | ------------------------- |
| Web corporativa pública |
| Servidor de correo |
| Pasarela VPN |
| Proxy (saliente e inverso) |
| HMI de planta y carpeta de planos |
| Autoridad de certificación (srv-ca) |
| Servidor de copias de seguridad |
| Portátiles de ingenieros y operarios |
| Wi-Fi de invitados |
| Servidor de registros y monitorización |
