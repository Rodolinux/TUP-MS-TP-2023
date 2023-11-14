## Normalizacion
* subrayado las pk
* negrita las fk

- FACTURACION(__Nro_comprobante (PK natural)__, **Id_cliente**, **Id_sucursal**, Tipo_Comprobante, Fecha_Comprobante, **Id_forma_de_pago**, **Id_docente**, Comision_docente,Pagado)

- DETALLE_FACTURACION(__Id_detalle (PK)__, **Nro_comprobante**,  **Id_item**, **id_curso**, Cantidad, Precio_unitario,Precio_iva)

- ITEMS(__Codigo (PK natural)__, Nombre, Descripcion, Precio_unitario,Precio_iva)

- CURSOS(__Id_curso (PK)__, Nombre, Descripcion_curso, Categoria_curso, Duracion_en_meses,Precio_vigente, Virtual_o_presencial, Localidad_presencial, **Id_docente**)

- SUCURSAL(__Punto_venta (PK natural)__,nombre,direccion,localidad,telefono)

- PERSONAS(__Dni (PK natural)__, Nombre, Direccion, Localidad, Codigo_postal, Telefono, Correo)

- USUARIO(__id_usuario (PK)__, **dni_persona**, contrasenia, **id_rol**)

- PROVEEDORES(__Id (PK)__, Nombre, Cuit, Tipo_iva, Direccion, Ciudad, Provincia, Tipo_insumo, Activo)

- ROL(__codigo (PK natural)__, nombre, descripcion)

- FORMA_PAGO(__Id (PK)__, Nombre, Descripcion)

- CLIENTES(__Id_cliente (PK)__, **Dni_persona**)

- DOCENTES(__Id_docente (PK)__, **Dni_persona**, comision)

- COMPRAS(__Id_compra (PK)__, **Id_proveedor**, Fecha, **Id_item**, Cantidad, Estado)

- STOCK_INVENTARIO(__Id_stock (PK)__, **Id_compra**, Fecha, Sucursal, Id_proveedor, Cantidad)