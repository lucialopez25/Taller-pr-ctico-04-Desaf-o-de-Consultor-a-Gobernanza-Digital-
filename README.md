# 

# **Propuesta técnica de implantación**

* # ***BLOQUE A:***

# 1.Análisis de mercado y selección

Tabla comparativa de estudio de mercado de los tres ERP:

| *Característica* | *Odoo* | *SAP S/4HANA* | *Zoho One* |
| :---: | :---: | :---: | :---: |
| Tipo | ERP modular | ERP corporativo | ERP todo en uno  |
| Tamaño empresa | Pequeña | Grande | Pequeña |
| Precio | bajo-medio | alto | bajo |
| Complejidad | Media | Alta | Baja |
| Personalización | Alta | Alta y difícil | Media |

Para una PYME de 25 empleados, presupuesto ajustado y necesidad de personalización en el etiquetado la mejor opción disponible sería Odoo Community. Nuestra decisión se basa en el análisis y la comparación entre la competencia, siendo SAP S/4HANA excesiva en coste y complejidad para el tamaño de la plantilla y Zoho One, aunque económico, menos flexible para modificaciones profundas en la etiquetación que requiere la empresa. Es por eso que Odoo, permitiendo acceso al código fuente para personalizar el etiquetado sin pagar licencias anuales por usuario e ideal para pequeñas empresas, es la mejor opción.

<img width="600" height="200" alt="image" src="https://github.com/user-attachments/assets/576e92df-cd85-4a27-ad21-c7519238e5da" />


## 2.Cálculo del TCO ( **Total Value of Ownership** o **Valor Total de Propiedad**. ) 3 años 

| *Concepto* | *Detalle* | *Coste*  |
| :---- | :---- | :---- |
| Licencias | Odoo Community | 0€ |
| Implantación | 100 horas x 40€ la hora | 4000€ |
| Hosting o alojamiento | Google cloud/huawei cloud/aws | 1800€ |
| Mantenimiento | Soporte técnico preventivo | 1200€ |
| Total (3 años) | Estimación  | 7000€ |

* # ***BLOQUE B:***

# 1\. Diseño de Seguridad RBAC

El [Principio del mínimo privilegio](https://www.paloaltonetworks.com/blog/2022/05/ztna-1-0-violates-principle-of-least-privilege/) es un concepto relacionado con la seguridad de la información según el cual un usuario sólo debe tener acceso a los datos, los recursos y las aplicaciones que necesite para llevar a cabo una determinada tarea. 

| *ROL* | *Ventas (CRM)* | *Almacén (STCOK)* | *Contabilidad* | *Configuración* |
| :---: | :---: | :---: | :---: | :---: |
| Administrador | total | total | total | total |
| Comercial | solo sus clientes | sin acceso | sin acceso | sin acceso |
| Operario de Almacén | sin acceso | Solo albaranes | sin acceso | sin acceso |
| Contable | solo lectura | sin acceso | Facturación | sin acceso |

\-Admin: Como responsable del sistema, necesita gestionar usuarios,etc… Necesita tener autoridad para poder supervisar los demás departamentos.

\-Comercial:  Se utilizan Record RULES para que el comercial no vea la cartera de clientes de sus compañeros.

\-Operario de almacén: Registra que entra y que sale físicamente del almacén.

\-Contable: Debe gestionar el flujo de cajas, impuestos y pagos. Necesita consultar los presupuestos aprobados para poder emitir las facturas correctamente.

* # ***BLOQUE C:***

\[En el repositorio de Github\]

# **Referencias:**

* **Ejercicio 1 bloque A:**

**Odoo (2026):** *Ediciones y Planes*. \[Web\]. **I:** Odoo ERP. **D:** Comparativa de versiones. **E:** Diferencia funciones gratuitas vs. de pago. **E:** [odoo.com/editions](https://www.odoo.com/es_ES/page/editions)  
**SAP (2026):** *Soluciones ERP Cloud*. \[Web\]. **I:** SAP S/4HANA. **D:** Software de gestión empresarial de alto nivel. **E:** Centralización de procesos complejos con IA. **E:** [sap.com/erp](https://www.sap.com/spain/products/erp.html)  
**Zoho (2026):** *Precios Zoho One*. \[Web\]. **I:** Zoho One Suite. **D:** Tarifas del ecosistema de aplicaciones. **E:** Modelo de licencia única para acceso total. **E:** [zoho.com/pricing](https://www.zoho.com/es-xl/one/pricing/)

* **Ejercicio 2 bloque A:** 

“Arquitectura, Seguridad y Gobernanza en Sistemas de Gestión Empresarial” UD7, 2026  
**Manutan (2026):** *Comprendiendo el TCO*. \[Web\]. **I:** Análisis de Coste Total de Propiedad. **D:** Guía sobre costes directos e indirectos de una compra. **E:** Explica cómo evaluar gastos ocultos más allá del precio de adquisición. **E:** [manutan.es/blog/tco](https://www.manutan.es/blog/comprendiendo-tco-total-cost-of-ownership/)  
**Investopedia (2026):** *Total Cost of Ownership (TCO)*. \[Web\]. **I:** Definición financiera de TCO. **D:** Recurso educativo sobre valoración de activos a largo plazo. **E:** Desglosa la metodología para calcular el valor real de sistemas y equipos. **E:** [investopedia.com/tco](https://www.investopedia.com/terms/t/totalcostofownership.asp)

* **Ejercicio 1 bloque B:**

**Palo Alto Networks (2026):** *Principio de Mínimo Privilegio*. \[Web\]. **I:** Seguridad informática (PoLP). **D:** Guía sobre restricción de accesos. **E:** Explica cómo limitar permisos para reducir la superficie de ataque. **E:** [paloaltonetworks.es/least-privilege](https://www.paloaltonetworks.es/cyberpedia/what-is-the-principle-of-least-privilege)  
**NIST (2026):** *Role-Based Access Control*. \[Web\]. **I:** Estándar RBAC. **D:** Proyecto de investigación sobre control de acceso basado en roles. **E:** Define el marco técnico para asignar permisos según funciones laborales. **E:** [csrc.nist.gov/rbac](https://csrc.nist.gov/projects/role-based-access-control)  
**Odoo S.A. (2026):** *Documentación Técnica 17.0*. \[Web\]. **I:** Seguridad en Odoo. **D:** Manual oficial de configuración del sistema. **E:** Describe la implementación práctica de grupos y permisos en el software. **E:** [odoo.com/documentation/17.0](https://www.odoo.com/documentation/17.0/es/)  
**Cybrosys (2026):** *Record Rules in Odoo 17*. \[Web\]. **I:** Reglas de Registro. **D:** Guía de desarrollo de seguridad a nivel de fila. **E:** Detalla cómo filtrar el acceso a datos específicos mediante código y dominios. **E:** [cybrosys.com/record-rules](https://www.cybrosys.com/odoo/odoo-books/odoo-17-development/security/record-rules/)

