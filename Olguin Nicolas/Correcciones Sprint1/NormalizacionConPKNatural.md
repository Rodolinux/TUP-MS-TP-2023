## Relacion Universal:

Bono (Anio PK, Mes PK, dni_empleado (FK a Empleado), rol_empleado (FK a Empleado), nombre_sucursal (FK a Sucursal), direccion_sucursal (FK a Sucursal), cod_pos_sucursal (FK a Sucursal), Total_produc􀆟vidad, Lleva_bono_glogal (si, no), Total_bono_capacitacion)
Stock (Fecha PK, nombre_item (FK a Item) PK, descripcion_item (FK a Item) PK, In_out PK, nombre_sucursal (FK a Sucursal), direccion_sucursal (FK a Sucursal), cod_pos_sucursal (FK a Sucursal), Can􀆟dad)
Item (Nombre PK, Descripcion PK, Precio_unitario, Precio_iva)
Sucursal (Nombre PK, Direccion PK, Codigo_postal PK, Ciudad, Provincia, Telefono, Correo)
Ventas (Fecha_venta PK, nombre_item (FK a item, puede ser NULL si no se refiere a un item), descripcion_item (FK a item, puede ser NULL si no se refiere a un item), Can􀆟dad_item, nombre_curso (FK a curso, puede ser NULL si no se refiere a un curso), Can􀆟dad_curso, Descuento)
Empleado_usuario_rol (Dni_empleado PK, Nombre_empleado PK,{ Dni_usuario PK (􀅅 a empleado), clave_usuario string PK },{ Dni_rol PK (􀅅 a empleado), acceso_rol PK (superadmin,auditor,gerente), descripción_rol })
Facturacion_puntoDeVenta_FormaDePago_Cliente (Nro_comprobante PK, Tipo_Comprobante PK, dni_Empleado (FK a Empleado), rol_Empleado (FK a Empleado), fecha_venta (FK a ventas), nombre_sucursal (FK a Sucursal), direccion_sucursal (FK a Sucursal), cod_pos_sucursal (FK a Sucursal),{ nombre_punto_de_venta (FK punto de venta)}, Fecha_Comprobante, {􀆟po_forma_de_pago (FK forma de pago), descripcion_forma_de_pago (FK forma de pago)},
{ Correo_cliente PK, Nombre, Direccion, Localidad, Código_postal, Teléfono } Pagado)
Cursos_Docente (Nombre_curso PK, Descripcion_curso, Categoria_curso, Duracion_en_meses, Precio_vigente, Virtual_o_presencial, Localidad_presencial,{ DNI_docente PK, Nombre_docente, Direccion_docente, Teléfono_docente, Correo_docente })
Compras_Proveedor (Fecha PK, Estado PK, nombre_item (FK a Item), descripcion_item (FK a Item), Can􀆟dad,{ (Cuit_proveedor PK, Nombre_ proveedor, Tipo_iva_ proveedor, Direccion_ proveedor, Ciudad_ proveedor, Provincia_ proveedor, Tipo_insumo_ proveedor, Ac􀆟vo_ proveedor })

## 3 FN:

Bono (Anio PK, Mes PK, dni_empleado (FK a Empleado), rol_empleado (FK a Empleado), nombre_sucursal (FK a Sucursal), direccion_sucursal (FK a Sucursal), cod_pos_sucursal (FK a Sucursal), Total_produc􀆟vidad, Lleva_bono_glogal (si, no), Total_bono_capacitacion)
Clientes (Correo PK, Nombre, Direccion, Localidad, Código_postal, Teléfono)
Stock (Fecha PK, nombre_item (FK a Item) PK, descripcion_item (FK a Item) PK, In_out PK, nombre_sucursal (FK a Sucursal), direccion_sucursal (FK a Sucursal), cod_pos_sucursal (FK a Sucursal), Can􀆟dad)
Facturacion (Nro_comprobante PK, Tipo_Comprobante PK, dni_Empleado (FK a Empleado), rol_Empleado (FK a Empleado), fecha_venta (FK a ventas), correo_cliente (FK a Clientes), nombre_sucursal (FK a Sucursal), direccion_sucursal (FK a Sucursal), cod_pos_sucursal (FK a Sucursal), nombre_punto_de_venta (FK punto de venta), Fecha_Comprobante, 􀆟po_forma_de_pago (FK forma de pago), descripcion_forma_de_pago (FK forma de pago), Pagado)
Cursos (Nombre PK, Descripcion_curso, Categoria_curso, Duracion_en_meses, Precio_vigente, Virtual_o_presencial, Localidad_presencial, dni_docente (FK a Docente))
Proveedores (Cuit PK, Nombre, Tipo_iva, Direccion, Ciudad, Provincia, Tipo_insumo, Ac􀆟vo)
Compras (Fecha PK, Estado PK, nombre_item (FK a Item), descripcion_item (FK a Item), Can􀆟dad, cuit_proveedor (FK a Proveedores))
Item (Nombre PK, Descripcion PK, Precio_unitario, Precio_iva)
Docente (DNI PK, Nombre, Direccion, Teléfono, Correo)
Empleado (Dni_empleado PK, Nombre_empleado PK)
Usuario (Dni_usuario PK (􀅅 a empleado), clave_usuario PK)
Rol (Dni_rol PK (􀅅 a empleado), acceso_rol PK (superadmin,auditor,gerente), descripcion_rol)
Sucursal (Nombre PK, Direccion PK, Codigo_postal PK, Ciudad, Provincia, Telefono, Correo)
PuntoVenta (Nombre_puntoVenta PK)
FormaPago (Tipo_formaPago PK, Descripcion_formaPago PK)
Ventas (Fecha_venta PK, nombre_item (FK a item, puede ser NULL si no se refiere a un item), descripcion_item (FK a item, puede ser NULL si no se refiere a un item), Can􀆟dad_item, nombre_curso (FK a curso, puede ser NULL si no se refiere a un curso), Can􀆟dad_curso, Descuento)
## Nota
Debido a que todas las tablas poseen atributos bien diferenciados entre si, pudimos realizar la normalizacion a 1 FN, quedando igual que la 3 FN.