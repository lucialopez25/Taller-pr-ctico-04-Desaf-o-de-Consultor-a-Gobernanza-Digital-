# 

# **Propuesta técnica de implantación**

# 1.Análisis de mercado y selección

Tabla comparativa de estudio de mercado de los tres ERP:

| *Característica* | *Odoo* | *SAP S/4HANA* | *Zoho One* |
| :---: | :---: | :---: | :---: |
| Tipo | ERP modular | ERP corporativo | ERP todo en uno  |
| Tamaño empresa | Pequeña | Grande | Pequeña |
| Precio | bajo-medio | alto | bajo |
| Complejidad | Media | Alta | Baja |
| Personalización | Alta | Alta y difícil | Media |

Para una PYME de 25 empleados, presupuesto ajustado y necesidad de personalización en el etiquetado la mejor opción disponible sería Odoo Community. Nuestra decisión se basa en el análisis y la comparación entre la competencia, siendo SAP S/4HANA excesiva en coste y complejidad para el tamaño de la plantilla y Zoho One, aunque económico, menos flexible en para modificaciones profundas en la etiquetación que requiere la empresa. Es por eso que Odoo, permitiendo acceso al código fuente para personalizar el etiquetado sin pagar licencias anuales por usuario e ideal para pequeñas empresas, es la mejor opción.

<img width="600" height="200" alt="image" src="https://github.com/user-attachments/assets/fe134a56-3a0c-4cd1-92e4-243acc661b93" />



## Cálculo del TCO ( **Total Value of Ownership** o **Valor Total de Propiedad**. ) 3 años 

| *Concepto* | *Detalle* | *Coste*  |
| :---- | :---- | :---- |
| Licencias | Odoo Community | 0€ |
| Implantación | 100 horas x 40€ la hora | 4000€ |
| Hosting o alojamiento | Google cloud/huawei cloud/aws | 1800€ |
| Mantenimiento | Soporte técnico preventivo | 1200€ |
| Total (3 años) | Estimación  | 7000€ |

# 

# 

# 

2\. Diseño de Seguridad RBAC

El [principio del mínimo privilegio](https://www.paloaltonetworks.com/blog/2022/05/ztna-1-0-violates-principle-of-least-privilege/) es un concepto relacionado con la seguridad de la información según el cual un usuario sólo debe tener acceso a los datos, los recursos y las aplicaciones que necesite para llevar a cabo una determinada tarea. 

| ROL | Ventas | Almacén | Contabilidad | Configuración |
| :---- | :---- | :---- | :---- | :---- |
| Administrador | total | total | total | total |
| Comercial | solo sus clientes | sin acceso | sin acceso | sin acceso |
| Operario de Almacén | sin acceso |  | sin acceso | sin acceso |
| Contable | solo lectura | sin acceso | Facturación | sin acceso |

\-El contable puede validar las facturas pero tiene bloqueada la modificación manual de niveles de stock

#  Referencias:

Ejercicio 2 bloque A:

* [https://www.odoo.com/es\_ES/page/editions](https://www.odoo.com/es_ES/page/editions)   
* [https://www.sap.com/spain/products/erp.html?pttid=7756\&campaigncode=crm-ya22-int-1517075\&source=ppc-es-googleads-search-19476048191-146874519098-clouderpgrow\_s4s-x-x-x\&gclsrc=aw.ds\&gad\_source=1\&gad\_campaignid=19476048191\&gbraid=0AAAAAoV5MAXWaD8X3zWdgoLULWp9zMmLd\&gclid=Cj0KCQjw\_IXQBhCkARIsADqELbKsnwoFUwwM1jTeSUovjckbhU3\_nKrw4l1BSKi74ALiKlspFCD08SsaAg7KEALw\_wcB](https://www.sap.com/spain/products/erp.html?pttid=7756&campaigncode=crm-ya22-int-1517075&source=ppc-es-googleads-search-19476048191-146874519098-clouderpgrow_s4s-x-x-x&gclsrc=aw.ds&gad_source=1&gad_campaignid=19476048191&gbraid=0AAAAAoV5MAXWaD8X3zWdgoLULWp9zMmLd&gclid=Cj0KCQjw_IXQBhCkARIsADqELbKsnwoFUwwM1jTeSUovjckbhU3_nKrw4l1BSKi74ALiKlspFCD08SsaAg7KEALw_wcB)   
* [https://www.zoho.com/es-xl/one/pricing/?src=one-header](https://www.zoho.com/es-xl/one/pricing/?src=one-header) 

“Arquitectura, Seguridad y Gobernanza en Sistemas de Gestión Empresarial” UD7, 2026

[https://www.manutan.es/blog/comprendiendo-tco-total-cost-of-ownership/?srsltid=AfmBOoqDpCL1X\_ygy3uKKV6zcMV1GlvsM3BvwPsuJVK4LvbYUxZwwJBJ](https://www.manutan.es/blog/comprendiendo-tco-total-cost-of-ownership/?srsltid=AfmBOoqDpCL1X_ygy3uKKV6zcMV1GlvsM3BvwPsuJVK4LvbYUxZwwJBJ)

[https://www.investopedia.com/terms/t/totalcostofownership.asp](https://www.investopedia.com/terms/t/totalcostofownership.asp)

\-Diseño de seguridad RBAC  
	\-Plan de Mínimo Privilegio  
[https://www.paloaltonetworks.es/cyberpedia/what-is-the-principle-of-least-privilege](https://www.paloaltonetworks.es/cyberpedia/what-is-the-principle-of-least-privilege)  
	\-RBAC  
[https://csrc.nist.gov/projects/role-based-access-control](https://csrc.nist.gov/projects/role-based-access-control)  
[https://www.odoo.com/documentation/17.0/es/](https://www.odoo.com/documentation/17.0/es/)  
