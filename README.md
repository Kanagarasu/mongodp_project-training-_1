# mongodp_project-training-_1
test> show dbs
// output
/*admin    40.00 KiB
config  108.00 KiB
local    40.00 KiB*/

test> use mydatabase
/*switched to db mydatabase*/

mydatabase> db.createCollection("Users");
/*{ ok: 1 }*/

mydatabase> db.Users.insertMany([{u_id:101,name:"kanagarasu",city:"truchi"},{u_id:102,name:"jeeva",city:"chennai"}])
/*{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('67ee0d3751866f974d6b140b'),
    '1': ObjectId('67ee0d3751866f974d6b140c')
  }
}*/

mydatabase> db.createCollection("Products");
/*{ ok: 1 }*/

mydatabase>db.Products.insertMany([{p_id:1,name:"phone",price:15000,category:"iphone",stock:100},{p_id:2,name:"laptop",price:45000,category:"hp"}])
/*{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('67ee0e8151866f974d6b140d'),
    '1': ObjectId('67ee0e8151866f974d6b140e')
  }
}*/

mydatabase> db.createCollection("Orders");
/*{ ok: 1 }*/

mydatabase> db.Orders.insertMany([{o_id:1,u_id:101,p_id:2,qty:1,status:"pending"},{o_id:2,u_id:102,p_id:1,qty:2,status:"delivered"}])
/*{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('67ee13e43824d667676b140b'),
    '1': ObjectId('67ee13e43824d667676b140c')
  }
}*/


mydatabase>db.Orders.insertMany([{pay_id:11,o_id:1,amount:45000,status:"pending",method:"online"},{pay_id:12,o_id:2,amount:30000,status:"delivered",method:"cash"}])
/*{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('67ee15393824d667676b140d'),
    '1': ObjectId('67ee15393824d667676b140e')
  }
}*/


mydatabase> db.createCollection("Payments");
{ ok: 1 }

mydatabase> db.Payments.insertMany([{pay_id:11,o_id:1,amount:45000,status:"pending",method:"online"},{pay_id:12,o_id:2,amount:30000,status:"delivered",method:"cash"}])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('67ee18653824d667676b140f'),
    '1': ObjectId('67ee18653824d667676b1410')
  }
}




