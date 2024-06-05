
access-list 1020 remark This ACL allows Sales from all floors to communicate with floor 7 Sales
access-list 1020 permit tcp 10.20.10.0 0.0.0.63 10.20.70.0 0.0.0.63 
access-list 1020 permit tcp 10.20.15.0 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.20.0 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.30.0 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.40.0 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.50.0 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.55.0 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.60.0 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.65.0 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.70.0 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.80.0 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 remark       
access-list 1020 remark This ACL allows Finance from all floors to communicate with floor 7 Sales
access-list 1020 permit tcp 10.20.10.64 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.15.64 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.20.64 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.30.64 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.40.64 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.50.64 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.55.64 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.60.64 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.65.64 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.70.64 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 permit tcp 10.20.80.64 0.0.0.63 10.20.70.0 0.0.0.63
access-list 1020 remark       
access-list 1020 remark This ACL allows Sales from all floors to communicate with floor 7 Finance
access-list 1020 permit tcp 10.20.10.0 0.0.0.63 10.20.70.64 0.0.0.63 
access-list 1020 permit tcp 10.20.15.0 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.20.0 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.30.0 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.40.0 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.50.0 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.55.0 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.60.0 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.65.0 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.70.0 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.80.0 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 remark       
access-list 1020 remark This ACL allows Finance from all floors to communicate with floor 7 Finance
access-list 1020 permit tcp 10.20.10.64 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.15.64 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.20.64 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.30.64 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.40.64 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.50.64 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.55.64 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.60.64 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.65.64 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.70.64 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 permit tcp 10.20.80.64 0.0.0.63 10.20.70.64 0.0.0.63
access-list 1020 remark       
access-list 1020 remark This ACL allows HR from all floors to communicate with floor 7 HR
access-list 1020 permit tcp 10.20.10.128 0.0.0.31 10.20.70.128 0.0.0.31
access-list 1020 permit tcp 10.20.15.128 0.0.0.31 10.20.70.128 0.0.0.31
access-list 1020 permit tcp 10.20.20.128 0.0.0.31 10.20.70.128 0.0.0.31
access-list 1020 permit tcp 10.20.30.128 0.0.0.31 10.20.70.128 0.0.0.31
access-list 1020 permit tcp 10.20.40.128 0.0.0.31 10.20.70.128 0.0.0.31
access-list 1020 permit tcp 10.20.50.128 0.0.0.31 10.20.70.128 0.0.0.31
access-list 1020 permit tcp 10.20.55.128 0.0.0.31 10.20.70.128 0.0.0.31
access-list 1020 permit tcp 10.20.60.128 0.0.0.31 10.20.70.128 0.0.0.31
access-list 1020 permit tcp 10.20.65.128 0.0.0.31 10.20.70.128 0.0.0.31
access-list 1020 permit tcp 10.20.70.128 0.0.0.31 10.20.70.128 0.0.0.31
access-list 1020 permit tcp 10.20.80.128 0.0.0.31 10.20.70.128 0.0.0.31
access-list 1020 remark
access-list 1020 remark This ACL allows HR from all floors to print to floor 7 MGMT
access-list 120 permit tcp 10.20.10.128 0.0.0.31 10.20.70.160 0.0.0.31 eq 9100
access-list 120 permit tcp 10.20.15.128 0.0.0.31 10.20.70.160 0.0.0.31 eq 9100
access-list 120 permit tcp 10.20.20.128 0.0.0.31 10.20.70.160 0.0.0.31 eq 9100
access-list 120 permit tcp 10.20.30.128 0.0.0.31 10.20.70.160 0.0.0.31 eq 9100
access-list 120 permit tcp 10.20.40.128 0.0.0.31 10.20.70.160 0.0.0.31 eq 9100
access-list 120 permit tcp 10.20.50.128 0.0.0.31 10.20.70.160 0.0.0.31 eq 9100
access-list 120 permit tcp 10.20.55.128 0.0.0.31 10.20.70.160 0.0.0.31 eq 9100
access-list 120 permit tcp 10.20.60.128 0.0.0.31 10.20.70.160 0.0.0.31 eq 9100
access-list 120 permit tcp 10.20.65.128 0.0.0.31 10.20.70.160 0.0.0.31 eq 9100
access-list 120 permit tcp 10.20.70.128 0.0.0.31 10.20.70.160 0.0.0.31 eq 9100
access-list 120 permit tcp 10.20.80.128 0.0.0.31 10.20.70.160 0.0.0.31 eq 9100
access-list 1020 remark       
access-list 1020 remark This ACL allows MGMT from all floors to communicate with floor 7 MGMT
access-list 1020 permit tcp 10.20.10.160 0.0.0.31 10.20.70.160 0.0.0.31
access-list 1020 permit tcp 10.20.15.160 0.0.0.31 10.20.70.160 0.0.0.31
access-list 1020 permit tcp 10.20.20.160 0.0.0.31 10.20.70.160 0.0.0.31
access-list 1020 permit tcp 10.20.30.160 0.0.0.31 10.20.70.160 0.0.0.31
access-list 1020 permit tcp 10.20.40.160 0.0.0.31 10.20.70.160 0.0.0.31
access-list 1020 permit tcp 10.20.50.160 0.0.0.31 10.20.70.160 0.0.0.31
access-list 1020 permit tcp 10.20.55.160 0.0.0.31 10.20.70.160 0.0.0.31
access-list 1020 permit tcp 10.20.60.160 0.0.0.31 10.20.70.160 0.0.0.31
access-list 1020 permit tcp 10.20.65.160 0.0.0.31 10.20.70.160 0.0.0.31
access-list 1020 permit tcp 10.20.70.160 0.0.0.31 10.20.70.160 0.0.0.31
access-list 1020 permit tcp 10.20.80.160 0.0.0.31 10.20.70.160 0.0.0.31
access-list 1020 remark
access-list 1020 remark This ACL allows MGMT from all floors to access the FTP file share on floor 7 Finance
access-list 120 permit tcp 10.20.10.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 20
access-list 120 permit tcp 10.20.10.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 21
access-list 120 permit tcp 10.20.15.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 20
access-list 120 permit tcp 10.20.15.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 21
access-list 120 permit tcp 10.20.20.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 20
access-list 120 permit tcp 10.20.20.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 21
access-list 120 permit tcp 10.20.30.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 20
access-list 120 permit tcp 10.20.30.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 21
access-list 120 permit tcp 10.20.40.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 20
access-list 120 permit tcp 10.20.40.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 21
access-list 120 permit tcp 10.20.50.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 20
access-list 120 permit tcp 10.20.50.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 21
access-list 120 permit tcp 10.20.55.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 20
access-list 120 permit tcp 10.20.55.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 21
access-list 120 permit tcp 10.20.60.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 20
access-list 120 permit tcp 10.20.60.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 21
access-list 120 permit tcp 10.20.65.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 20
access-list 120 permit tcp 10.20.65.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 21
access-list 120 permit tcp 10.20.70.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 20
access-list 120 permit tcp 10.20.70.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 21
access-list 120 permit tcp 10.20.80.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 20
access-list 120 permit tcp 10.20.80.160 0.0.0.31 10.20.70.64 0.0.0.63 eq 21
access-list 1020 remark       
access-list 1020 remark This ACL allows NT admin from all floors to communicate with floor 7 NT admin
access-list 1020 permit tcp 10.20.10.192 0.0.0.15 10.20.70.192 0.0.0.15
access-list 1020 permit tcp 10.20.15.192 0.0.0.15 10.20.70.192 0.0.0.15
access-list 1020 permit tcp 10.20.20.192 0.0.0.15 10.20.70.192 0.0.0.15
access-list 1020 permit tcp 10.20.30.192 0.0.0.15 10.20.70.192 0.0.0.15
access-list 1020 permit tcp 10.20.40.192 0.0.0.15 10.20.70.192 0.0.0.15
access-list 1020 permit tcp 10.20.50.192 0.0.0.15 10.20.70.192 0.0.0.15
access-list 1020 permit tcp 10.20.55.192 0.0.0.15 10.20.70.192 0.0.0.15
access-list 1020 permit tcp 10.20.60.192 0.0.0.15 10.20.70.192 0.0.0.15
access-list 1020 permit tcp 10.20.65.192 0.0.0.15 10.20.70.192 0.0.0.15
access-list 1020 permit tcp 10.20.70.192 0.0.0.15 10.20.70.192 0.0.0.15
access-list 1020 permit tcp 10.20.80.192 0.0.0.15 10.20.70.192 0.0.0.15
access-list 1020 remark   
access-list 1020 remark This ACL denies Guests from any floor to communicate with floor 7 Guests
access-list 1020 deny ip any host 10.20.70.208 0.0.0.15
int range g1/0/1-2
ip access-group 1020 in
end
copy run start






Sales:
10.20.70.0 255.255.255.192  0.0.0.63
Fin:
10.20.70.64 255.255.255.192 0.0.0.63
HR:
10.20.70.128 255.255.255.224 0.0.0.31
MGMT:
10.20.70.160 255.255.255.224 0.0.0.31
NT-ADMIN:
10.20.70.192 255.255.255.240 0.0.0.15
Guest:
10.20.70.208 255.255.255.240 0.0.0.15