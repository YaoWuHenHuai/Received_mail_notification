#!/bin/bash

##need to have a system/sistema mail so the server could send out messages
function count_loop {
count=0
while IFW= read -r line
do
        count=$((count+1))
done < "fechas"
}

if [ -d d ]; then
        count_loop
        first_count=$(echo "$count")
        rm -r d
else
        first_count=0
fi
[ -d d ] || mkdir d
cd d
user="santiago"
domain="veljos.com"
doveadm search -u "$user" mailbox INBOX subject "" | while read guid uid; do doveadm fetch -u "$user" body mailbox-guid "$guid" uid "$uid" > "$uid" ; done
ls > f

while IFW= read -r line
do
        while IFW= read -r raw
        do
                [[ "$raw" =~ "Date: " ]] && echo "$raw" >> fechas
        done < "$line"
done < "f"
count=0
count_loop
second_count=$(echo "$count")
[[ "$first_count" == "$second_count" ]] || echo "your domains mail has received a message, please verify" | mail -a FROM:sistema@"$domain" "$user"@"$domain" --subject="Mai>
