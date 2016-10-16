# KitchenAppWebservice
{\rtf1\ansi\ansicpg1252\deff0\nouicompat\deflang1033{\fonttbl{\f0\fnil\fcharset0 Calibri;}{\f1\fnil Lucida Console;}{\f2\fnil Source Code Pro;}}
{\colortbl ;\red0\green0\blue255;\red255\green0\blue0;}
{\*\generator Riched20 10.0.14393}\viewkind4\uc1 
\pard\sa200\sl276\slmult1\qc\ul\b\f0\fs36\lang9 Kitchen App API Documentation\par

\pard\sa200\sl276\slmult1\ulnone\fs22\par
\fs24 BASE-URL\fs22 : \par
\tab {\b0{\field{\*\fldinst{HYPERLINK http://127.0.0.1/codeigniter/index.php/api }}{\fldrslt{http://127.0.0.1/codeigniter/index.php/api\ul0\cf0}}}}\f0\fs22\par
\fs24 HEADERS\fs22 :\par

\pard\li720\sa200\sl276\slmult1\b0 Authorization: Basic YWRtaW46MTIzNA==\par
API-KEY: gcok0cw0gc4gg0480csgoowkoc0s8g040g4kk8kg\par
Content-Type: application/x-www-form-urlencoded\b\par
\par

\pard\sa200\sl276\slmult1 **NOTE\b0\line response will always contain "Error" object \line Example:\par

\pard\cf2\f1\fs18\lang1033\{"Error":\{"error_code":1,"message":"invalid or missing parameters"\}\}\par
\cf0\fs17\par
\f0\fs22 if \b error_code \b0 is \b 1\b0  dont parse the response further, just show \b message \b0 in Toast/Log\par
\f1\fs17\par
\par
\par
\par
\par
\par
\par
\f0\fs22\lang9\par

\pard\sa200\sl276\slmult1\ul\b\fs24 USER RELATED METHODS\b0\fs22\par
\ulnone 1) Create new user\par
\tab method type: \b PUT\par
\tab\b0 method url: \b /User\b0\par
\tab put parameters: \par
\tab\tab\b first_name\par
\tab\tab last_name\par
\tab\tab email\par
\tab\tab password\par
\tab\tab display_name\par
\tab\tab pin \b0 (optional)\par
\par
2) Login\par
\tab method type: \b POST\par
\b0\tab method url: \b /User/try_login\b0\par
\tab post parameters:\par
\tab\tab\b email\par
\tab\tab password\par
\par
\b0 3) Add new user role\par
\tab method type: \b PUT\b0\par
\tab method url: \b /UserRole\b0\par
\tab put parameters: \par

\pard\box\brdrdash\brdrw0 \sa200\sl276\slmult1\tab\tab\b\f2\fs21 role_name\par
\f0\fs22\tab\tab\f2\fs21 role_added_by\par
\f0\fs24\par

\pard\sa200\sl276\slmult1\par
\ul MENU RELATED METHODS\b0\fs22\par
\ulnone 1) Get menu\par
\tab method type: \b GET\b0\par
\tab method url: \b /MenuItem\par
\par
\b0 2) Add new menu item\par
\tab method type: \b PUT\b0\par
\tab method url: \b /MenuItem\b0\par
\tab put parameters: \par

\pard\box\brdrdash\brdrw0 \sa200\sl276\slmult1\tab\tab\b\f2\fs21 name\par
\f0\fs22\tab\tab\f2\fs21 category_id\par
\f0\fs22\tab\tab\f2\fs21 price\par
\f0\fs22\tab\tab\f2\fs21 description\f0\lang1033  \b0 (optional)\b\f2\lang9\par
\f0\fs22\tab\tab\f2\fs21 image_url\f0\lang1033  \b0 (optional)\b\f2\lang9\par

\pard\sa200\sl276\slmult1\b0\f0\fs22\par
3) Get menu item category\par
\tab method type: \b GET\par
\tab\b0 method url: \b /MenuItemCategory\par
\par
\b0 4) Add menu item category\par
\tab method type: \b PUT\b0\par
\tab method url: \b /MenuItemCategory\par
\b0\tab put parameters: \par

\pard\box\brdrdash\brdrw0 \sa200\sl276\slmult1\tab\tab\b\f2\fs21 category_name\par
\f0\fs24\tab\tab\f2\fs21 super_category\par

\pard\sa200\sl276\slmult1\b0\f0\fs22\par
\par
\ul\b\fs24 ORDER RELATED METHODS\fs22\par
\ulnone\b0 1) Get all orders\par
\tab method type: \b PUT\b0\par
\tab method url: \b /Order\b0\par
\line 2) Place new order\par
\tab method type: \b PUT\fs24\par
\tab\b0 method url: \b /Order\par

\pard\li720\sa200\sl276\slmult1\b0\fs22 put parameters: \b\fs24\tab\b0\fs22\par
\b\tab data\par
\b0 data format:\par
\b\{\par
"order_name":"rakshit bhai",\par
"order_table":"2",\par
"order_status":"1",\par
"order_taken_by":"1",\par
"order_items":[\par
\tab\tab\{"orderitem_menu_item":"1","orderitem_quantity":"2","orditem_status":"1"\},\par
\tab\tab\{"orderitem_menu_item":"2","orderitem_quantity":"3","orditem_status":"2"\},\par
\tab\tab\{"orderitem_menu_item":"3","orderitem_quantity":"5","orditem_status":"1"\},\par
\tab ],\par
\}\par
\par

\pard\sa200\sl276\slmult1\b0\fs24 3) get order item status\par
\tab\par
4) change order item status\par
\tab method type: POST\par
\tab method url: /OrderItem/change_item_status\par
\tab post parameters: \par

\pard\box\brdrdash\brdrw0 \sa200\sl276\slmult1\tab\tab\b\f2\fs21 orderitem_id\par
\f0\lang1033\tab\tab\f2 orderitem_status\par
\f0\tab\tab\f2 updated_by\ul\f0\fs24\lang9\par

\pard\sa200\sl276\slmult1\par
TABLE INFO RELATED METHODS\fs22\par
\ulnone\b0 1) get all table info\par
\tab method type: \b GET\b0\par
\tab method url: \b /TableInfo\par
\par
\b0 2) add table info \par
\tab method type: \b PUT\b0\par
\tab method url: \b /TableInfo\par
\b0\tab put parameters: \par

\pard\box\brdrdash\brdrw0 \sa200\sl276\slmult1\b\tab\tab\f2\fs21 table_name\par
\f0\fs22\tab\tab\f2\fs21 table_shape\par
\f0\fs22\tab\tab\f2\fs21 table_position\par
\f0\fs22\tab\tab\f2\fs21 table_size\par
\f0\fs22\tab\tab\f2\fs21 table_capacity\par
\f0\fs22\tab\tab\f2\fs21 table_status\f0\fs22\par
}
