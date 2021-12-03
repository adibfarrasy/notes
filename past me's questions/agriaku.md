## Questions about Agriaku Webserver v2

## Domain Module

### DomainServiceModule.kt
INSTALL THE SERVICE MODULES (authentication, mitra, notification)
    - how does com.google.inject.AbstractModule work? TO IMPLEMENT configure() AND CALL THE METHODS WHICH MIRROR THOSE FOUND IN BINDER.

### authentication/AuthenticationServiceModule
INJECT THE AUTHENTICATION PORTS WITH THEIR RESPECTIVE BUSINESS LOGIC
    - what is bind(XService::class.java).to(XServiceImpl::class.java).asEagerSingleton() for? BINDING AN INTERFACE WITH ITS IMPLEMENTATION
    - what is binding anyway? INJECT AN OBJECT X TO A CLASS Y, LEAVING THE INSTANTIATION OF X OUT OF THE INSTANTIATION OF Y (NO new KEYWORD INSIDE CLASS Y). THIS IS MORE MODULAR AND EASIER TO TEST. IN AGRIAKU'S CASE, IT IS TO CREATE A SINGLETON.

### authentication/OTPVerificationServiceImpl
OTP BUSINESS LOGIC
    - what is @Inject for and how to use it? INJECT A CONSTRUCTOR. IN JAVA CAN BE USED TO INJECT FIELD AND METHOD AS WELL.
    - what is companion object and when to use it? FOR OBJECT DECLARATION INSIDE A CLASS. THE OBJECT CAN HAVE FIELDS AND METHODS.
    - when to use coroutineScope { launch { ... } }? TO WRITE ASYNC NON-BLOCKING CODE (DON'T HAVE TO WAIT FOR THE RESULTS TO BE RECEIVED BEFORE CONTINUING THE PROGRAM)
    - what is logger and when to use logger? TO LOG API AT DEPLOYMENT

### authentication/EmailVerificationServiceImpl
EMAIL VERIFICATION BUSINESS LOGIC

### authentication/ApplicationServiceImpl
APPLICATION GETTER/SETTER BUSINESS LOGIC

### authentication/AuthorizationServiceImpl
LOGIN/ LOGOUT BUSINESS LOGIC
    - where the function returns something, where does it go next? (same with all the other business logic) THEY'RE RETURNED INSIDE THE CLASS THAT CALLS ITS INSTANCE, THE SERVICE FUNCTION IS INJECTED INTO THE DOMAIN SERVICE, WHICH IS INJECTED INTO THE MAIN APPLICATION.

### authentication/UserServiceImpl
USER CRUD BUSINESS LOGIC

### mitra/MitraServiceModule
INJECT MITRA PORTS WITH THEIR RESPECTIVE BUSINESS LOGIC (ONLY 1)

### mitra/MitraServiceImpl
MITRA CRUD BUSINESS LOGIC

### notification/NotificationServiceModule
INJECT NOTIFICATION PORTS WITH THEIR RESPECTIVE BUSINESS LOGIC (ONLY 1)

### notification/NotificationServiceImpl
REGISTER/DEACTIVATE TOKEN
    - how is the registration/ deactivation token related to notification? IT'S A MISNOMER. THE API IS USED TO REGISTER/ DEACTIVATE TOKEN FOR USER DEVICE TO RECEIVE NOTIFICATIONS.

## Ports Module
ALL OBJECT DEFINITIONS ARE LOCATED IN PORTS. FUNCTION INPUT-OUTPUT DEFINITIONS ARE PLACED IN INTERFACES, WHILE DATA OBJECT ARE STORED IN DATA CLASS.

### accessor/authentication/ApplicationAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR APPLICATION ACCESSOR ADAPTER
    - what is :: in Exception::class used for? A REFLECTION. IT GETS ACCESS TO THE CLASS, CONSTRUCTORS AND METHODS. TO TURN IT INTO A JAVA REFLECTION, SIMPLY ADD .java i.e. Exception::class.java
    - what is @Throws? what do they do? DECLARES WHAT EXCEPTION SHOULD BE THROWN WHEN COMPILED TO A JVM METHOD.
KOTLIN:
@Throws(IOException::class)
fun readFile(name: String): String {...}

IS TRANSLATED TO JAVA:
String readFile(String name) throws IOException {...}

### accessor/authentication/EmailVerificationAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR EMAIL VERIFICATION ACCESSOR ADAPTER

### accessor/authentication/OTPVerificationAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR OTP VERIFICATION ACCESSOR ADAPTER

### accessor/authentication/OTPVerificationAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR OTP VERIFICATION ACCESSOR ADAPTER

### accessor/authentication/ResourceAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR RESOURCE ACCESSOR ADAPTER

### accessor/authentication/RoleAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR ROLE ACCESSOR ADAPTER

### accessor/authentication/RoleResourceMappingAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR ROLE RESOURCE MAPPING ACCESSOR ADAPTER

### accessor/authentication/SessionAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR SESSION ACCESSOR ADAPTER

### accessor/authentication/UserAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR USER ACCESSOR ADAPTER

### accessor/authentication/UserDeviceAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR USER DEVICE ACCESSOR ADAPTER

### accessor/authentication/UserEntityMappingAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR USER ENTITY MAPPING ACCESSOR ADAPTER

### accessor/authentication/UserResourceMappingAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR USER RESOURCE MAPPING ACCESSOR ADAPTER

### accessor/authentication/UserRoleMappingAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR USER ROLE MAPPING ACCESSOR ADAPTER

### accessor/firestore/data/FarmerFirestoreData
DEFINE THE SHAPE OF FARMER DATA IN FIRESTORE

### accessor/firestore/data/GeolocationFirestoreData
DEFINE THE SHAPE OF GEOLOCATION DATA IN FIRESTORE

### accessor/firestore/data/TokenFirestoreData
DEFINE THE SHAPE OF TOKEN DATA IN FIRESTORE
    - what is platform & token, how are they used? PLATFORM IS DEVICE TYPE, TOKEN IS FIREBASE TOKEN. NO IMPLEMENTATION IN CODE SO NOT 100% SURE.

### accessor/firestore/data/UserEmployeeFirestoreData
DEFINE THE SHAPE OF USER EMPLOYEE DATA IN FIRESTORE

### accessor/firestore/data/UserFranchiseFirestoreData
DEFINE THE SHAPE OF USER FRANCHISE DATA IN FIRESTORE

### accessor/firestore/UserEmployeeFirestoreAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR USER EMPLOYEE FIRESTORE ACCESSOR ADAPTER

### accessor/firestore/UserFranchiseFirestoreAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR USER FRANCHISE FIRESTORE ACCESSOR ADAPTER

### accessor/mitra/MitraDetailAccessor
INTERFACE WITH ONLY @Throws(Exception::class) AND FUNCTION DEFINITIONS FOR MITRA DETAIL ACCESSOR ADAPTER

### api/APIError
DEFINE THE SHAPE OF API ERROR DATA (ONLY STATUS & MESSAGE)

### api/ErrorCodeEnum
DEFINE DIFFERENT ERROR CODE NAMES IN ENUM CLASS

### api/Response
DEFINE THE RESPONSE DATA (ONLY DATA GENERICS AND ERROR CODE) IN OPEN CLASS
    - why use open class? OPEN CLASS FOR EXTENSION (INHERITANCE)
    - why is the value declared? SEEMS TO BE FOR DEFAULT VALUE

### conf/Conf
SEEMS TO STORE ALL CONFIG, INCLUDING ENVIRONMENT NAMES, DB DETAILS, API_KEYS, ETC

### data/ApplicationEnum
DEFINE DIFFERENT APPLICATION TYPE (MITRA, HUB, FARMER) IN ENUM CLASS

### data/PlatformEnum
DEFINE DIFFERENT PLATFORM TYPE (WEB, ANDROID, IOS, IOT) IN ENUM CLASS

### data/ResourceEnum
DEFINE RESOURCE IN ENUM CLASS (ONLY GOT 1 ENTRY SO FAR: REGISTER_DEVICE_TOKEN)
    - what is this used for? ONLY USED TO DISPLAY A MESSAGE IN REGISTER/ DEACTIVATE TOKEN API ROUTE

### data/RoleEnum
DEFINE ROLE IN ENUM CLASS (ONLY GOT 1 ENTRY SO FAR: MITRA)

### generated/*
ALL FILES GENERATED BY JOOQ

### service/MODULE_NAME/data/*Spec
DEFINE THE MODULE FUNCTION INPUT SHAPE

### service/MODULE_NAME/data/*Result
DEFINE THE MODULE FUNCTION OUTPUT SHAPE

### service/MODULE_NAME/*Service
INTERFACES THAT DEFINE THE FUNCTIONS FOR EACH MODULE CLASS

### utils/AndroidAppHashGenerator
CONTAINS AN ENCAPSULATED FUNCTION THAT GENERATES A HASH

### utils/CryptoUtils
CONTAINS ENCAPSULATION FUNCTIONS FOR ENCRYPTION (encrypt, decrypt, validatePassword, etc.)

## Adapters Module

### accessor/AccessorModule
INSTALL THE ACCESSOR MODULES (AuthenticationAccessorModule, MitraAccessorModule)

### accessor/AgriakuDatasource
EMPTY ANNOTATION CLASS AgriakuDatasource
    - what is annotation class? KOTLIN SPECIFIC CLASS INTEROPERABLE WITH JAVA ANNOTATION CLASS 
    - what is @BindingAnnotation and how to use it? AN ANNOTATION CLASS TO BIND A CLASS WITH ITS ANNOTATION
    - what does 'datasource' refer to here? SEEMS TO BE THE DATABASE SOURCE

### accessor/AgriakuFirestore
EMPTY ANNOTATION CLASS AgriakuFirestore

### accessor/DSLModule
CONFIG FOR DATABASE
    - what is HikariConfig and when to use it? A JAVA CONFIG CLASS USED TO INITIALIZE A DATA SOURCE (DATABASE)
    - what is HikariDataSource and how to use it? AN INSTANCE OF DATA SOURCE CONNECTION WITH THE CONFIGURATION
    - what is bind(DSLContext::class.java).annotatedWith(AgriakuDatasource::class.java).toInstance(dslContext) and what is it for? SEEMS LIKE TO EXPORT THE dslContext SO THAT IT CAN BE USED OUTSIDE THE FILE, JUST CALL THE INSTANCE NAME WITH THE ANNOTATION

### accessor/FirestoreModule
CONFIG FOR FIRESTORE

### accessor/authentication/AuthenticationAccessorModule
INJECT THE AUTHENTICATION ACCESSOR PORTS WITH THEIR IMPLEMENTATIONS AND ENFORCE SINGLETON INSTANCES

### accessor/authentication/ApplicationAccessorImpl
SQL QUERY FOR APPLICATION

### accessor/authentication/EmailVerificationAccessorImpl
SQL QUERY FOR EMAIL

### accessor/authentication/OTPVerificationAccessorImpl
SQL QUERY FOR OTP VERIFICATION

### accessor/authentication/ResourceAccessorImpl
SQL QUERY FOR RESOURCE

### accessor/authentication/RoleAccessorImpl
SQL QUERY FOR ROLE

### accessor/authentication/RoleResourceMappingImpl
SQL QUERY FOR ROLE RESOURCE MAPPING

### accessor/authentication/SessionAccessorImpl
SQL QUERY FOR SESSION

### accessor/authentication/UserAccessorImpl
SQL QUERY FOR USER

### accessor/authentication/UserDeviceAccessorImpl
SQL QUERY FOR USER DEVICE

### accessor/authentication/UserEntityMappingAccessorImpl
SQL QUERY FOR USER ENTITY MAPPING

### accessor/authentication/UserResourceMappingAccessorImpl
SQL QUERY FOR USER RESOURCE MAPPING

### accessor/authentication/UserRoleMappingAccessorImpl
SQL QUERY USER ROLE MAPPING

### accessor/firestore/UserEmployeeFirestoreAccessorImpl
FIRESTORE QUERY FOR USER EMPLOYEE FIRESTORE

### accessor/firestore/UserFranchiseFirestoreAccessorImpl
FIRESTORE QUERY FOR USER FRANCHISE FIRESTORE
    - how to use channel? CONCEPTUALLY SIMILAR TO BLOCKING QUEUE BUT IT CAN BE CLOSED
    - how to use runBlocking? SIMILAR TO NODEJS AWAIT, IT RUNS ASYNC FUNCTIONS SYNCHRONOUSLY. NOT SUPPOSED TO BE RUN IN PRODUCTION?

### accessor/mitra/MitraAccessorModule
INJECT MITRA ACCESSOR INTERFACE INTO ITS IMPLEMENTATION AND ENFORCE THE SINGLETON

### accessor/mitra/MitraAccessorImpl
SQL QUERY FOR MITRA


