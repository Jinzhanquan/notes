#!/bin/bash

HOST='127.0.0.1'  #-h
PORT='3306'       #-P
USER='root'       #-u
PASSWORD='Fangle12#$' #-p
DB='urpcs'
INIT_SQL=(urpcs.sql urpcs1.sql urpcs2.sql)
POTH='./sql/'
CMD='help'

array=()
function split()
{
  split_ret=${1//=/ }
  count=0
  for e in $split_ret
  do
    array[$count]=$e
    let count++
  done
}


function init()
{
    echo "init command"
    for arg in  ${INIT_SQL[@]}
    do
       echo 111:$arg 
       cat $POTH$arg | mysql -u$USER -p$PASSWORD $DB
    done
        mysql -u$USER -p$PASSWORD -e "show tables from $DB"
}


function help()
{
  echo 'help function'
  echo ' ./migrate  [-param=value] <cmd>    -- cmd format'
  echo 'parameters:'
  echo ' -h                                 - mysql host ip address '
  echo ' -p                                 - mysql host port '
  echo 'cmd:'
  echo ' init                               - init databse'
  echo 'example:'
  echo './migrate                           -- get help '
  echo './migrate init                      -- init databse'
}


function up_cmd()
{
  echo 'up cmd'

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
        -u)
          USER=${array[1]}
          echo "replace user:"$USER
        ;;
        -P)
          PORT=${array[1]}
          echo "replace port:"$PORT
        ;;
        init|up|down|help)
          CMD=${array[0]}
        ;;
        *)
          echo "do not know:"${array[0]}
        ;;
  esac
  done



  case $CMD in
     init)
         init
       ;;
       up)
         up_cmd
       ;;
     help)
         help
       ;;
  esac
