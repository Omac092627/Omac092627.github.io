##Databse


Do some research on what a Database Schema is.What is a Schema?A database schema is the skeleton structure that represents the logical view of the entire database.Why do we use them?It defines how the data is organized and how the relations among them are associated. It formulates all the constraints that are to be applied on the data.What do they look like?a TableWhat are the different types of Database Keys?What is a Primary Key? This column, or columns, is called the primary key (PK) of the table and enforces the entity integrity of the table.What is a Foreign Key?A foreign key (FK) is a column or combination of columns that is used to establish and enforce a link between the data in two tables to control the data that can be stored in the foreign key table.What is a Composite Key?Composite key is a combination of more than one attributes that can be used to uniquely identity each record. It is also known as “Compound” key. A composite key may be a candidate or primary key.How are they different? When do you use 1 over the others?Primary is used for standard columns in the table. Foreign key is if you have to link information used for two separate tables. Composite key is a combination of more than one attribute, i.e primary and foreign are usually one I believe. What are Relationships in a relational database?What is a 1:1 relationship? In a one-to-one relationship, one record in a table is associated with one and only one record in another table. What is a Many:Many relationship?A many-to-many relationship refers to a relationship between tables in a database when a parent row in one table contains several child rows in the second table, and vice versa.How about a 1: Many or a Many:1?In a relational database, a one-to-many relationship exists when one row in table A may be linked with many rows in table B, but one row in table B is linked to only one row in table 


Characteristics
Traditionally, data was organized in file formats. DBMS was a new concept then, and all the research was done to make it overcome the deficiencies in traditional style of data management. A modern DBMS has the following characteristics −

Real-world entity − A modern DBMS is more realistic and uses real-world entities to design its architecture. It uses the behavior and attributes too. For example, a school database may use students as an entity and their age as an attribute.

Relation-based tables − DBMS allows entities and relations among them to form tables. A user can understand the architecture of a database just by looking at the table names.

Isolation of data and application − A database system is entirely different than its data. A database is an active entity, whereas data is said to be passive, on which the database works and organizes. DBMS also stores metadata, which is data about data, to ease its own process.

Less redundancy − DBMS follows the rules of normalization, which splits a relation when any of its attributes is having redundancy in values. Normalization is a mathematically rich and scientific process that reduces data redundancy.

Consistency − Consistency is a state where every relation in a database remains consistent. There exist methods and techniques, which can detect attempt of leaving database in inconsistent state. A DBMS can provide greater consistency as compared to earlier forms of data storing applications like file-processing systems.

Query Language − DBMS is equipped with query language, which makes it more efficient to retrieve and manipulate data. A user can apply as many and as different filtering options as required to retrieve a set of data. Traditionally it was not possible where file-processing system was used.

ACID Properties − DBMS follows the concepts of Atomicity, Consistency, Isolation, and Durability (normally shortened as ACID). These concepts are applied on transactions, which manipulate data in a database. ACID properties help the database stay healthy in multi-transactional environments and in case of failure.

Multiuser and Concurrent Access − DBMS supports multi-user environment and allows them to access and manipulate data in parallel. Though there are restrictions on transactions when users attempt to handle the same data item, but users are always unaware of them.

Multiple views − DBMS offers multiple views for different users. A user who is in the Sales department will have a different view of database than a person working in the Production department. This feature enables the users to have a concentrate view of the database according to their requirements.

Security − Features like multiple views offer security to some extent where users are unable to access data of other users and departments. DBMS offers methods to impose constraints while entering data into the database and retrieving the same at a later stage. DBMS offers many different levels of security features, which enables multiple users to have different views with different features. For example, a user in the Sales department cannot see the data that belongs to the Purchase department. Additionally, it can also be managed how much data of the Sales department should be displayed to the user. Since a DBMS is not saved on the disk as traditional file systems, it is very hard for miscreants to break the code.
---
The DataType attribute
For student enrollment dates, all of the web pages currently display the time along with the date, although all you care about for this field is the date. By using data annotation attributes, you can make one code change that will fix the display format in every view that shows the data. To see an example of how to do that, you'll add an attribute to the EnrollmentDate property in the Student class.

In Models/Student.cs, add a using statement for the System.ComponentModel.DataAnnotations namespace and add DataType and DisplayFormat attributes to the EnrollmentDate property, as shown in the following example:

The DataType attribute is used to specify a data type that's more specific than the database intrinsic type. In this case we only want to keep track of the date, not the date and time. The DataType Enumeration provides for many data types, such as Date, Time, PhoneNumber, Currency, EmailAddress, and more. The DataType attribute can also enable the application to automatically provide type-specific features. For example, a mailto: link can be created for DataType.EmailAddress, and a date selector can be provided for DataType.Date in browsers that support HTML5. The DataType attribute emits HTML 5 data- (pronounced data dash) attributes that HTML 5 browsers can understand. The DataType attributes don't provide any validation.
---
The ApplyFormatInEditMode setting specifies that the formatting should also be applied when the value is displayed in a text box for editing. (You might not want that for some fields -- for example, for currency values, you might not want the currency symbol in the text box for editing.)

You can use the DisplayFormat attribute by itself, but it's generally a good idea to use the DataType attribute also. The DataType attribute conveys the semantics of the data as opposed to how to render it on a screen, and provides the following benefits that you don't get with DisplayFormat:

The browser can enable HTML5 features (for example to show a calendar control, the locale-appropriate currency symbol, email links, some client-side input validation, etc.).

By default, the browser will render data using the correct format based on your locale.
---
The StringLength attribute
You can also specify data validation rules and validation error messages using attributes. The StringLength attribute sets the maximum length in the database and provides client side and server side validation for ASP.NET Core MVC. You can also specify the minimum string length in this attribute, but the minimum value has no impact on the database schema.

Suppose you want to ensure that users don't enter more than 50 characters for a name. To add this limitation, add StringLength attributes to the LastName and FirstMidName properties, as shown in the following example:

The StringLength attribute won't prevent a user from entering white space for a name. You can use the RegularExpression attribute to apply restrictions to the input. For example, the following code requires the first character to be upper case and the remaining characters to be alphabetical:
---
The MaxLength attribute provides functionality similar to the StringLength attribute but doesn't provide client side validation.
---
The database model has now changed in a way that requires a change in the database schema. You'll use migrations to update the schema without losing any data that you may have added to the database by using the application UI.

Save your changes and build the project. Then open the command window in the project folder and enter the following commands:
---
The migrations add command warns that data loss may occur, because the change makes the maximum length shorter for two columns. Migrations creates a file named <timeStamp>_MaxLengthOnNames.cs. This file contains code in the Up method that will update the database to match the current data model. The database update command ran that code.

The timestamp prefixed to the migrations file name is used by Entity Framework to order the migrations. You can create multiple migrations before running the update-database command, and then all of the migrations are applied in the order in which they were created.

Run the app, select the Students tab, click Create New, and try to enter either name longer than 50 characters. The application should prevent you from doing this.
---
The Column attribute
You can also use attributes to control how your classes and properties are mapped to the database. Suppose you had used the name FirstMidName for the first-name field because the field might also contain a middle name. But you want the database column to be named FirstName, because users who will be writing ad-hoc queries against the database are accustomed to that name. To make this mapping, you can use the Column attribute.

The Column attribute specifies that when the database is created, the column of the Student table that maps to the FirstMidName property will be named FirstName. In other words, when your code refers to Student.FirstMidName, the data will come from or be updated in the FirstName column of the Student table. If you don't specify column names, they're given the same name as the property name.

In the Student.cs file, add a using statement for System.ComponentModel.DataAnnotations.Schema and add the column name attribute to the FirstMidName property, as shown in the following highlighted code:

The addition of the Column attribute changes the model backing the SchoolContext, so it won't match the database.

Save your changes and build the project. Then open the command window in the project folder and enter the following commands to create another migration:
---
The Required attribute
The Required attribute makes the name properties required fields. The Required attribute isn't needed for non-nullable types such as value types (DateTime, int, double, float, etc.). Types that can't be null are automatically treated as required fields.

The Required attribute must be used with MinimumLength for the MinimumLength to be enforced.
---
The Display attribute
The Display attribute specifies that the caption for the text boxes should be "First Name", "Last Name", "Full Name", and "Enrollment Date" instead of the property name in each instance (which has no space dividing the words).
---
The FullName calculated property
FullName is a calculated property that returns a value that's created by concatenating two other properties. Therefore it has only a get accessor, and no FullName column will be generated in the database.

The CourseAssignments and OfficeAssignment navigation properties
The CourseAssignments and OfficeAssignment properties are navigation properties.

An instructor can teach any number of courses, so CourseAssignments is defined as a collection.

If a navigation property can hold multiple entities, its type must be a list in which entries can be added, deleted, and updated. You can specify ICollection<T> or a type such as List<T> or HashSet<T>. If you specify ICollection<T>, EF creates a HashSet<T> collection by default.

The reason why these are CourseAssignment entities is explained below in the section about many-to-many relationships.

Contoso University business rules state that an instructor can only have at most one office, so the OfficeAssignment property holds a single OfficeAssignment entity (which may be null if no office is assigned).
---
The Key attribute
There's a one-to-zero-or-one relationship between the Instructor and the OfficeAssignment entities. An office assignment only exists in relation to the instructor it's assigned to, and therefore its primary key is also its foreign key to the Instructor entity. But the Entity Framework can't automatically recognize InstructorID as the primary key of this entity because its name doesn't follow the ID or classnameID naming convention. Therefore, the Key attribute is used to identify it as the key:

You can also use the Key attribute if the entity does have its own primary key but you want to name the property something other than classnameID or ID.

By default, EF treats the key as non-database-generated because the column is for an identifying relationship.

The Instructor navigation property
The Instructor entity has a nullable OfficeAssignment navigation property (because an instructor might not have an office assignment), and the OfficeAssignment entity has a non-nullable Instructor navigation property (because an office assignment can't exist without an instructor -- InstructorID is non-nullable). When an Instructor entity has a related OfficeAssignment entity, each entity will have a reference to the other one in its navigation property.

You could put a [Required] attribute on the Instructor navigation property to specify that there must be a related instructor, but you don't have to do that because the InstructorID foreign key (which is also the key to this table) is non-nullable.
---
The DatabaseGenerated attribute
The DatabaseGenerated attribute with the None parameter on the CourseID property specifies that primary key values are provided by the user rather than generated by the database.

y default, Entity Framework assumes that primary key values are generated by the database. That's what you want in most scenarios. However, for Course entities, you'll use a user-specified course number such as a 1000 series for one department, a 2000 series for another department, and so on.

The DatabaseGenerated attribute can also be used to generate default values, as in the case of database columns used to record the date a row was created or updated. 
---
Foreign key and navigation properties
The foreign key properties and navigation properties in the Course entity reflect the following relationships:

A course is assigned to one department, so there's a DepartmentID foreign key and a Department navigation property for the reasons mentioned above.
---

The Column attribute
Earlier you used the Column attribute to change column name mapping. In the code for the Department entity, the Column attribute is being used to change SQL data type mapping so that the column will be defined using the SQL Server money type in the database:

Column mapping is generally not required, because the Entity Framework chooses the appropriate SQL Server data type based on the CLR type that you define for the property. The CLR decimal type maps to a SQL Server decimal type. But in this case you know that the column will be holding currency amounts, and the money data type is more appropriate for that.

Foreign key and navigation properties
The foreign key and navigation properties reflect the following relationships:

A department may or may not have an administrator, and an administrator is always an instructor. Therefore the InstructorID property is included as the foreign key to the Instructor entity, and a question mark is added after the int type designation to mark the property as nullable. The navigation property is named Administrator but holds an Instructor entity: