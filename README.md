CREATE TABLE Admin (
    id          INT NOT NULL,
    username    VARCHAR(100)NOT NULL,
    email       VARCHAR(100)NOT NULL,
    password    VARCHAR(50)NOT NULL,
    phone       VARCHAR(20)NOT NULL,
    PRIMARY KEY (id)
);

CREATE TABLE Category (
    cid          INTEGER NOT NULL GENERATED ALWAYS AS IDENTITY (START WITH 1, INCREMENT BY 1),
    name            VARCHAR(100) NOT NULL,
    image           VARCHAR(45) ,
    PRIMARY KEY (cid)
);

CREATE TABLE Customer (
    userid          INT NOT NULL,
    name            VARCHAR(100) NOT NULL,
    email           VARCHAR(45) NOT NULL,
    password        VARCHAR(45) NOT NULL,
    phone           VARCHAR(20) NOT NULL,
    gender          VARCHAR(20) NOT NULL,
    registerdate    TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    address         VARCHAR(250),
    city            VARCHAR(100),
    pincode         VARCHAR(10),
    state           VARCHAR(100),
    PRIMARY KEY (userid),
    UNIQUE (email),
    UNIQUE (phone)
);

CREATE TABLE PRODUCT (
    pid INTEGER NOT NULL GENERATED ALWAYS AS IDENTITY (START WITH 1, INCREMENT BY 1),
    name VARCHAR(100) NOT NULL,
    description VARCHAR(500),
    price VARCHAR(20) NOT NULL,
    quantity int,
    discount int,
    image varchar(100),
    cid int,
    PRIMARY KEY (pid)
);

CREATE TABLE ORDERED_PRODUCT (
    oid INTEGER NOT NULL GENERATED ALWAYS AS IDENTITY (START WITH 1, INCREMENT BY 1),
    name VARCHAR(100),
    quantity INTEGER,
    price VARCHAR(45),
    image VARCHAR(100),
    orderid INTEGER,
    PRIMARY KEY (oid)
);

CREATE TABLE WISHLIST(
    idwishlist INTEGER NOT NULL GENERATED ALWAYS AS IDENTITY (START WITH 1, INCREMENT BY 1),
    iduser INTEGER,
    idproduct INTEGER,
    PRIMARY KEY (idwishlist)
);

CREATE TABLE CART(
    id INTEGER NOT NULL GENERATED ALWAYS AS IDENTITY (START WITH 1, INCREMENT BY 1),
    uid INTEGER NOT NULL,
    pid INTEGER NOT NULL,
    quantity INTEGER NOT NULL,
    PRIMARY KEY (id)
);

CREATE TABLE ORDER_TABLE(
    id INTEGER NOT NULL GENERATED ALWAYS AS IDENTITY (START WITH 1, INCREMENT BY 1),
    orderid VARCHAR(100),
    status VARCHAR(100),
    paymentType VARCHAR(100),
    userId INTEGER,
    date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (id)
);

CREATE TABLE CART(
    id INTEGER NOT NULL GENERATED ALWAYS AS IDENTITY (START WITH 1, INCREMENT BY 1),
    uid INTEGER NOT NULL,
    pid INTEGER NOT NULL,
    quantity INTEGER NOT NULL,
);

CREATE TABLE MANAGER(
   password varchar(20)
)
