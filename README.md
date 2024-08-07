CREATE SCHEMA FERRETERIA;
USE FERRETERIA;
CREATE TABLE clientes(
id_cliente INT NOT NULL,
dni VARCHAR(15),
nombre VARCHAR(100),
phone VARCHAR(15),
mail VARCHAR(50),
PRIMARY KEY(id_cliente)
);
INSERT INTO clientes(id_cliente, dni, nombre, phone, mail) VALUES
(1, 16456258-4, 'Andres', 965847596, 'andresss@gmail.com'),
(2, 12058423-5, 'Sofia', 982075698, 'sofi20@gmail.com'),
(3, 6513458-9, 'Carlos', 920658788, 'carsveloz@gmail.com'),
(4, 21231696-8, 'Daniela', 912459596, 'dannini@gmail.com'),
(5, 20235689-4, 'Manuel', 962548796, 'manu1313@gmail.com'),
(6, 25897664-5, 'Lub', 945228996, 'lubby@gmail.com'),
(7, 22505613-9, 'Marilyn', 925641396, 'agrupacion@gmail.com');

CREATE TABLE despacho(
id_despacho INT NOT NULL,
id_cliente INT NOT NULL,
id_venta INT NOT NULL,
fecha DATE,
PRIMARY KEY(id_despacho)
);
INSERT INTO despacho(id_despacho, id_cliente, id_venta, fecha) VALUES
(1, 1, 1, '2024-10-25'),
(2, 2, 2, '2024-10-27'),
(3, 3, 3, '2024-11-01'),
(4, 4, 4, '2024-11-02'),
(5, 5, 5, '2024-11-05'),
(6, 6, 6, '2024-11-12'),
(7, 7, 7, '2024-11-21');

CREATE TABLE productos(
id_productos INT NOT NULL,
id_cliente INT NOT NULL,
herramientas VARCHAR(100),
hogar VARCHAR(100),
electricidad VARCHAR(100),
construccion VARCHAR(100),
hidraulico VARCHAR(100),
PRIMARY KEY(id_productos)
);
INSERT INTO productos(id_productos, id_cliente, herramientas, hogar, electricidad, construccion, hidraulico) VALUES
(1, 1, 'martillo', 'lampara', 'cable rvk', 'cemento', 'tubo pvc'), 
(2, 2, 'combo', 'ceramica', 'lampara', 'zinc acanalado 3.5', 'codo pvc'),
(3, 3, 'desatornillador', 'repisa', 'zapatilla 4 puestos', 'plancha o.s.b', 'curva pvc'),
(4, 4, 'alicate', 'puerta', 'enchufe macho', 'bekron', 'copla pvc'),
(5, 5, 'asadon', 'cuchillo', 'tubo conduit', 'escalera metalica', 'union americana'),
(6, 6, 'hacha', 'tostador', 'cable eva rojo', 'casco', 'bushing pvc'),
(7, 7, 'huincha', 'embudo', 'alargador 10mts', 'guante cabritilla', 'tee pvc');

CREATE TABLE proveedores(
id_proveedores INT NOT NULL,
id_productos INT NOT NULL,
costo FLOAT NOT NULL,
fecha DATE,
nombre VARCHAR(100),
PRIMARY KEY(id_proveedores)
);
INSERT INTO proveedores(id_proveedores, id_productos, costo, fecha, nombre) VALUES
(1, 1, 2100, '2024-05-26', 'solito spa'), 
(2, 2, 3500, '2024-05-28', 'andrades eirl'),
(3, 3, 800, '2024-06-01', 'malito sa'),
(4, 4, 680, '2024-06-03', 'chipi chipi spa'),
(5, 5, 3000, '2024-06-05', 'bueeee sa'),
(6, 6, 4500, '2024-06-12', 'fulbito spa'),
(7, 7, 3200, '2024-06-15', 'masomenos eirl');

CREATE TABLE ventas(
id_venta INT NOT NULL,
id_cliente INT NOT NULL,
fecha DATE,
total FLOAT,
PRIMARY KEY(id_venta)
);
INSERT INTO ventas(id_venta, id_cliente, fecha, total) VALUES
(1, 1, '2024-07-26', 2400), 
(2, 2, '2024-07-28', 4100),
(3, 3, '2024-08-01', 1400),
(4, 4, '2024-08-03', 1200),
(5, 5, '2024-08-05', 4100),
(6, 6, '2024-08-12', 5350),
(7, 7, '2024-08-15', 4100);
