# TUP - Metodología de sistemas - 2023
Grupo Laria, Main, Petraglia

# Normalizacion:
Item_Por_Factura(id_item(PK), precio_unitario,precio_iva,canmtidad,id_movimiento_facturacion(FK))

Cursos(id_curso(PK), nombre, descripcion_curso, duracion_en_meses, precio_vigente, virtual_o_presencial, legajo_docente(FK))

Facturacion(id_movimiento_facturacion(PK), id_cliente(FK), nombre_sucursal(FK), id_punto_de_venta(FK), tipo_comprobante, fecha_comprobante, id_forma_de_pago(FK), legajo_docente(FK), comision_docente, tipo(FK))

Forma_Pago(id_forma_de_pago(FK), tipo_pago, detalle)

Punto_De_Venta(id_punto_de_venta(PK), nombre, descripcion)

Docente(legajo_docente(PK),Dni_Persona(FK))

Cliente(id_Cliente(PK),Dni_Persona(FK))

Persona(Dni_Persona(PK), nombre, telefono, correo, codigo_postal(FK), descripcion)

Usuario(id_usuario(PK), Dni_persona(FK), id_rol(FK))

Rol(id_rol(PK), descripcion)

Localidad(codigo_postal(PK), direccion, localidad)

Sucursal(id_sucursal(PK), nombre, direccion, codigo_postal(FK))

Empleado(legajo_empleado(PK), Dni_Personal(FK), cargo)

Bono(id_bono(PK), fecha, legajo_empleado(FK), lleva_bono_global, total_bono_capacitacion, id_sucursal(FK), total_productividad)

Stock(nro_stock(PK), id_item(FK), id_proveedor(FK), sucursal(FK), cantidad, in_out)

Proveedor(id_proveedor(PK), tipo_iva, tipo_insumo, activo)

Compras(id_compras(PK), id_proveedor(FK), fecha, id_articulo(FK), cantidad, estado)

Articulo(id_articulo(PK), nombre, precio)

Items(id_item(PK), nombre, precio, precio_iva)

