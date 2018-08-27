#!/bin/bash

HOST='127.0.0.1'  #-h
PORT='3306'       #-P
USER='root'       #-u
PASSWORD='123456' #-p
DB='urpcs'
INIT_SQL=(URPCS.SQL ORDINARY.sql AUTHORITY.sql PROCEDURE.sql)

array=()
function split(){
  split_ret=${1//=/ }
  count=0
  for e in $split_ret
  do 
    array[$count]=$e
    let count++
  done 
}


for arg in $*
do 
  split $arg
  case ${array[0]} in
        -h)
          HOST=${array[1]}
          echo "replace host:"$HOST
        ;;
        -p)
          PASSWORD=${array[1]}
          echo "replace password:"$PASSWORD
        ;;
        up)
          echo "up command"
        ;;
        init)
          echo "init command"
        ;;
        *)
        echo "do not know:"${array[0]}
        ;;
  esac
done