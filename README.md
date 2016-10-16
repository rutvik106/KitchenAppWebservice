# KitchenAppWebservice

Kitchen App API Documentation

BASE-URL: 
	http://127.0.0.1/codeigniter/index.php/api
HEADERS:
Authorization: Basic YWRtaW46MTIzNA==
API-KEY: gcok0cw0gc4gg0480csgoowkoc0s8g040g4kk8kg
Content-Type: application/x-www-form-urlencoded

**NOTE
response will always contain "Error" object 
Example:
{"Error":{"error_code":1,"message":"invalid or missing parameters"}}

if error_code is 1 dont parse the response further, just show message in Toast/Log








USER RELATED METHODS
1) Create new user
	method type: PUT
	method url: /User
	put parameters: 
		first_name
		last_name
		email
		password
		display_name
		pin (optional)

2) Login
	method type: POST
	method url: /User/try_login
	post parameters:
		email
		password

3) Add new user role
	method type: PUT
	method url: /UserRole
	put parameters: 
		role_name
		role_added_by


MENU RELATED METHODS
1) Get menu
	method type: GET
	method url: /MenuItem

2) Add new menu item
	method type: PUT
	method url: /MenuItem
	put parameters: 
		name
		category_id
		price
		description (optional)
		image_url (optional)

3) Get menu item category
	method type: GET
	method url: /MenuItemCategory

4) Add menu item category
	method type: PUT
	method url: /MenuItemCategory
	put parameters: 
		category_name
		super_category


ORDER RELATED METHODS
1) Get all orders
	method type: PUT
	method url: /Order

2) Place new order
	method type: PUT
	method url: /Order
put parameters: 	
	data
data format:
{
"order_name":"rakshit bhai",
"order_table":"2",
"order_status":"1",
"order_taken_by":"1",
"order_items":[
		{"orderitem_menu_item":"1","orderitem_quantity":"2","orditem_status":"1"},
		{"orderitem_menu_item":"2","orderitem_quantity":"3","orditem_status":"2"},
		{"orderitem_menu_item":"3","orderitem_quantity":"5","orditem_status":"1"},
	],
}

3) get order item status
	
4) change order item status
	method type: POST
	method url: /OrderItem/change_item_status
	post parameters: 
		orderitem_id
		orderitem_status
		updated_by

TABLE INFO RELATED METHODS
1) get all table info
	method type: GET
	method url: /TableInfo

2) add table info 
	method type: PUT
	method url: /TableInfo
	put parameters: 
		table_name
		table_shape
		table_position
		table_size
		table_capacity
		table_status
