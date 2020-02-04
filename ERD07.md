# ERD 07

## Martin Notation

![](/Users/quirin/Documents/3AHITM/Informationssysteme/Uebungen/ERD07/erd07.png)

## UML Notation
![](/Users/quirin/Documents/3AHITM/Informationssysteme/Uebungen/ERD07/IMG_0659.JPG)

## Relations

Employee = (**pk**:ssn, name, salary, **fk**:storage-building(Storage-Building:city))
Clerk = (**(fk,pk)**:snn(Employee:ssn), bonus)
Worker = (**(fk,pk)**:snn(Employee:ssn), forklift_flag)

Storage-Building = (**pk**:city, **fk**:boss-snn, capazity, **fk**:storage(Storage:**id**))
Storage = (quantity, quality, **(fk, pk)**:wine_type(Wine-Type:id))
Wine-Type = (**pk**: id)
Wine = (**fk**:type(Wine-Type:id), **pk**: description, **pk**: harvest-year, **(pk, fk)**: origin(Wineyard:id))
Wineyard = (**pk**:id, name, **fk**: wine-type(Wine-Type:id))

Order = (**(fk, pk)**: storage-building(Storage-Building:city), **(fk, pk)**: customer(Customer:id))
Orderpos. = (**pk**: number, **fk**: wine(Wine_Type:id), amount, **fk**: order(Order:(storage-building, customer)))
Customer = (**pk**: id,  name, address)
