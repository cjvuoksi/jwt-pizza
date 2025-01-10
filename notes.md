# Learning notes

## JWT Pizza code study and debugging

As part of `Deliverable ⓵ Development deployment: JWT Pizza`, start up the application and debug through the code until you understand how it works. During the learning process fill out the following required pieces of information in order to demonstrate that you have successfully completed the deliverable.

| User activity                                       | Frontend component | Backend endpoints | Database SQL |
| --------------------------------------------------- | ------------------ | ----------------- | ------------ |
| View home page                                      |     home.tsx       |     none          |  none        |
| Register new user<br/>(t@jwt.com, pw: test)         |     register.tsx   | \[Post\] /api/auth |  INSERT INTO user (name,email, password) VALUES (?, ?, ?) <br/> INSERT INTO userRole (userId, role, objectId) VALUES (?, ?, ?)   |
| Login new user<br/>(t@jwt.com, pw: test)            |     login.tsx      | \[Put\] /api/auth  |  SELECT * FROM user WHERE email=? <br/> SELECT * FROM userRole WHERE userId=? <br/> INSERT INTO auth (token, userId) VALUES (?, ?)            |
| Order pizza                                         |  menu.tsx <br/> payment.tsx <br/> delivery.tsx                  |    \[Get\] /api/order/menu <br/> TODO:FIXME (franchiseRouter) \[Post\] /api/order  <br/> \[Post\] FactoryURL + /api/order            |   SELECT * FROM menu <br/> INSERT INTO dinerOrder (dinerId, franchiseId, storeId, date) VALUES (?, ?, ?, now()) <br/> INSERT INTO orderItem (orderId, menuId, description, price) VALUES (?, ?, ?, ?)         |
| Verify pizza                                        |      delivery.tsx              |  \[Post\]   factoryURL + /api/order/verify              |    none          |
| View profile page                                   |      dinerDashboard.tsx              |  \[Get\] /api/order   |      SELECT id, franchiseId, storeId, date FROM dinerOrder WHERE dinerId=? LIMIT ${offset},${config.db.listPerPage} <br/>  SELECT id, menuId, description, price FROM orderItem WHERE orderId=?       |
| View franchise<br/>(as diner)                       |     franchiseDashboard.tsx              |      \[Get\] /api/franchise/:userID             |              |
| Logout                                              |                    |                   |              |
| View About page                                     |                    |                   |              |
| View History page                                   |                    |                   |              |
| Login as franchisee<br/>(f@jwt.com, pw: franchisee) |                    |                   |              |
| View franchise<br/>(as franchisee)                  |                    |                   |              |
| Create a store                                      |                    |                   |              |
| Close a store                                       |                    |                   |              |
| Login as admin<br/>(a@jwt.com, pw: admin)           |                    |                   |              |
| View Admin page                                     |                    |                   |              |
| Create a franchise for t@jwt.com                    |                    |                   |              |
| Close the franchise for t@jwt.com                   |                    |                   |              |
