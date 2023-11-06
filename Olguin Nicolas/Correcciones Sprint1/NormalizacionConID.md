## Relación Universal:

Empleado_usuario_rol (Id_legajo pk, Nombre_empleado, Dni_empleado, {Id_usuario, contraseña_usuario},{ Id_rol, acceso_rol, descripcion_rol})
Bono (Id_bono pk, Anio, Mes, Id_legajo_􀅅, Id_sucursal_􀅅, Total_produc􀆟vidad, Lleva_bono_global, Total_bono_capacitacion)
Stock (Id_movimiento_stock pk, Fecha, Id_item_􀅅, Id_sucursal_􀅅, Can􀆟dad, In_out)
Facturacion_puntoDeVenta_FormaDePago_Cliente (Id_facturacion pk, Id_Empleado_􀅅, Id_venta_􀅅, Nro_comprobante, Tipo_Comprobante, Fecha_Comprobante, {Id_punto_de_venta_􀅅, Nombre} ,{Id_forma_de_pago_􀅅, Tipo, Descripcion}, Pagado, {Id_cliente pk, Nombre, Direccion, Localidad, Código_postal, Teléfono, Correo})
Cursos_Docente (Id_curso pk, Nombre_curso, Descripcion_curso, Categoria_curso, Duracion_en_meses, Precio_vigente, Virtual_o_presencial, Localidad_presencial,{ Id_docente pk, Nombre, DNI, Direccion, Teléfono, Correo})
Compras_Proveedor (Id_compra pk, Fecha, Id_item_􀅅, Can􀆟dad, Estado,{ Id_proveedor pk, Nombre, Cuit, Tipo_iva, Direccion, Ciudad, Provincia, Tipo_insumo, Ac􀆟vo})
Item (Id_item pk, Nombre, Descripcion, Precio_unitario, Precio_iva)
Ventas (Id_venta pk, Fecha_venta, Id_item_􀅅, Can􀆟dad_item, Id_curso_􀅅, Can􀆟dad_curso, Descuento)
Sucursal (Id_sucursal pk, Nombre, Ciudad, Provincia, Direccion, Codigo_postal, Telefono, Correo)

## 3 FN

Bono (id_bono pk, Anio (YYYY), Mes (MM), Id_legajo (􀅅 a Empleado), Id_sucursal (􀅅 a Sucursal), Total_produc􀆟vidad, Lleva_bono_global (si, no), Total_bono_capacitacion)
Stock (Id_movimiento_stock pk, Fecha, Id_item (􀅅 a Item), Id_sucursal (􀅅 a Sucursal), Can􀆟dad, In_out)
Clientes (Id_cliente pk, Nombre, Direccion, Localidad, Código_postal, Teléfono, Correo)
Facturacion (Id_facturacion pk, Id_Empleado (􀅅 a Empleado), Id_venta (􀅅 a Ventas), Id_sucursal (􀅅 a Sucursal), Id_punto_de_venta (􀅅 a PuntoVenta), Id_cliente (􀅅 a Cliente), Nro_comprobante, Tipo_Comprobante, Fecha_Comprobante, Id_forma_de_pago (􀅅 a FormaPago), Pagado)
Cursos (Id_curso pk, Nombre, Descripcion_curso, Categoria_curso, Duracion_en_meses, Precio_vigente, Virtual_o_presencial, Localidad_presencial, Id_docente (􀅅 a Docente))
Proveedores (Id_proveedor pk, Nombre, Cuit, Tipo_iva, Direccion, Ciudad, Provincia, Tipo_insumo, Ac􀆟vo)
Compras (Id_compra pk, Id_proveedor (􀅅 a Proveedores), Fecha, Id_item (􀅅 a Item), Can􀆟dad, Estado)
Item (Id_item pk, Nombre, Descripcion, Precio_unitario, Precio_iva)
Docente (Id_docente pk, Nombre, DNI, Direccion, Teléfono, Correo)
Empleado (Id_legajo pk, Nombre, Dni, Id_usuario (􀅅 a Usuario))
Usuario (Id_usuario pk, contraseña, Id_rol (􀅅 a Rol))
Rol (Id_rol pk, acceso, descripcion)
Sucursal (Id_sucursal pk, Nombre, Ciudad, Provincia, Direccion, Codigo_postal, Telefono, Correo)
PuntoVenta (Id_punto_de_venta pk, Nombre)
FormaPago (Id_forma_de_pago pk, Tipo, Descripcion)
Ventas (Id_venta pk, Fecha_venta, Id_item (􀅅 a Item, puede ser NULL si no se refiere a un item), Can􀆟dad_item, Id_curso (􀅅 a Curso, puede ser NULL si no se refiere a un curso), Can􀆟dad_curso, Descuento)

## Nota

Debido a que todas las tablas tienen Id artificiales, al comenzar a normalizar la relacion Universal, ya nos queda en 3 FN de manera directa