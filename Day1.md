## sql server exception

* **Question** today when use the dapper access the MSSQL,the script is ok,but when execute throw followwing exception

*asp.net ExecuteReader requires an open and available Connection. The connection's current state is open* 

 * **Answer**  
   i want figure out why got this error
   A:https://stackoverflow.com/questions/33497253/asp-net-executereader-requires-an-open-and-available-connection-the-connection
    In practice, most applications use only one or a few different configurations for connections.
    This means that during application execution, many identical connections will be repeatedly opened and closed. 
    To minimize the cost of opening connections, ADO.NET uses an optimization technique called connection pooling.
    Connection pooling reduces the number of times that new connections must be opened.
    The pooler maintains ownership of the physical connection. 
    It manages connections by keeping alive a set of active connections for each given connection configuration.
    Whenever a user calls Open on a connection, the pooler looks for an available connection in the pool. If a pooled connection is available, it returns it to the caller instead of opening a new connection. When the application calls Close on the connection, the pooler returns it to the pooled set of active connections instead of closing it. 
    Once the connection is returned to the pool, it is ready to be reused on the next Open call.

   https://forums.iis.net/t/1192605.aspx
   
   https://social.msdn.microsoft.com/Forums/en-US/32ce6136-006f-40b4-9853-4906ff16232e/executereader-requires-an-open-and-available-connection-the-connections-current-state-is-open?forum=adodotnetdataproviders

    