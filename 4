package main

import (
        "fmt"
        "io/ioutil"
        "net/http"
        "database/sql"
       _"github.com/Go-SQL-Driver/MySQL"
        "reflect"
)
func main() {
        http.HandleFunc("/test", hand)
        http.HandleFunc("/register",register)
        err := http.ListenAndServe(":8080", nil)
        if err != nil {
                fmt.Println("err")
        }
}
func hand(w http.ResponseWriter, r *http.Request) {
        db,err := sql.Open("mysql","root:root@tcp(localhost:3306)/yttzcom?charset=utf8")
         nam := r.FormValue("name")
         pas := r.FormValue("pasw")
        query, err := db.Query("select * from tmpdb.tmptab where name = '"+nam+"' and  psw = '"+pas+"'") 
        checkErr(err)
        v := reflect.ValueOf(query)
        fmt.Println(v)
        //number := printResult(query)
        dates :=printResult(query)
         w.Write([]byte(dates))
        defer r.Body.Close()
}
func register(w http.ResponseWriter, r *http.Request){
        fmt.Println("register")
        w.Write([]byte("there is register!"))

        defer r.Body.Close()
        body, err := ioutil.ReadAll(r.Body)
        if err != nil {
            fmt.Println("read err")
        }
        fmt.Println(string(body))
}
func checkErr(errMasg error) {  
        if errMasg != nil {  
                panic(errMasg)  
        }  
}
func printResult(query *sql.Rows) string  { 
        column, _ := query.Columns()              //读出查询出的列字段名  
        values := make([][]byte, len(column))     //values是每个列的值，这里获取到byte里  
        scans := make([]interface{}, len(column)) //因为每次查询出来的列是不定长的，用len(column)定住当次查询的长度  
        for i := range values {                   //让每一行数据都填充到[][]byte里面  
                scans[i] = &values[i]  
        }  
        results := make(map[int]map[string]string) //最后得到的map  
        i := 0  
        for query.Next() { //循环，让游标往下移动  
                if err := query.Scan(scans...); err != nil { //query.Scan查询出来的不定长值放到scans[i] = &values[i],也就是每行都放在values里  
                        fmt.Println(err)  
                        return  "3"
                }  
                row := make(map[string]string) //每行数据  
                for k, v := range values {     //每行数据是放在values里面，现在把它挪到row里  
                        key := column[k]  
                        row[key] = string(v)  
                }  
                results[i] = row //装入结果集中  
                i++  
        }       
        for k, v := range results { //查询出来的数组
                 fmt.Println(k)
                 fmt.Println(v)
                 record :="<b>登陆成功</b>\nid:"+results[k]["id"]+"\n"+"用户名:"+results[k]["name"]+"\n"+"密码:"+results[k]["psw"]                
                 return record               
        }
        return "<b>用户名或密码错误</b>"        
}
