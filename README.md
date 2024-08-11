const mysql = require('mysql');
const con = mysql.createConnection({
  host: '****************************************************************',
  user: '******',
  port:"****",
  password: '**********',
  database: '**********',
});

exports.handler = (event, context, callback) => {
  // allows for using callbacks as finish/error-handlers
  context.callbackWaitsForEmptyEventLoop = false;
  const sql = "INSERT INTO tb_estado (estado) VALUES ('"+event.estado+"')";
  con.query(sql, (err, res) => {
    if (err) {
      throw err
    }
    callback(null, 'Se registro valor.');
  });
    
};
