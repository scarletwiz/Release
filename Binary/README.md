# Release Version 

Recommend Version for the new project is 1.1.0.8.<BR>
AT+CIUPDATE<BR>
An OTA URL is http://wizwiki.net/download/WizFi360/O11/WizFi360_SDK.img.<BR>

Recommend Version for existing project is 1.0.7.3.<BR>
AT+CIUPDATE<BR>
An OTA URL is http://wizwiki.net/download/WizFi360/WizFi360_SDK.img.<BR>

## Released 1.1.0.8<BR>
 20200903<BR>

1. Added SUB Topic 2, max 5 sub topic

2. Added MQTTPUBDEX command

3. Added AWS MQTT topic 4 in aws_app_int()

4. Changed HOSTIF_TASK_STK_SIZE 500 → 1200(If SPI SSL connect, error "task[uart sp] prio[45]stack over flow")

5. Fixed auto connection sequence when using AT command "AT+SAVETRANSLINK"

	TCP auto connection was normal, but UDP auto connection was defective. → UDP auto connection is normal.

6. Fixed "AT+CWSAP" maxconn

	Fixed the maximum number of stations are connected to softap.

7. Fixed defects that do not set the maximum number of stations are connected to softap

	Used function "tls_wifi_softap_set_sta_num()".

## Released 1.0.7.3<BR>
 20200903<BR>

1. Fixed AT+CWSTARTSMART

	When it started WebServer, at_wifiMode was still station. And it had printed STAIP on Command CIFSR.

2. Added Error Message of autoconnect

	When it prepared autoconnect, there was no message of the reason for failure.

3. Fixed auto connection & transparent mode sequence when using AT command "AT+SAVETRANSLINK"

	TCP auto connection & transparent mode was normal, but UDP auto connection & transparent mode was defective. → UDP auto connection & transparent mode is normal.

4. Fixed "AT+CWSAP" maxconn

	Fixed the maximum number of stations are connected to softap.

## Released 1.1.0.7<BR>
 20200413<BR>
 For the new project<BR>

1.  Added AT+AWSCON<BR>

2.  Added AT+AWSPKSEND<BR>

3.  Added AT+CLICASEND<BR>

4.  Fixed AutoConnect<BR>
    When it connected to AP automatically, it didn't back up mode value of parameters, so the wrong value(0) was written to flash. After reset, its mode value of parameters was 0, and then it didn't try to connect to AP automatically.

## Released 1.1.0.6<BR>
 20200309<BR>
 For the new project<BR>

1.  Added AT+WIZ_NETCONFIG<BR>
    WebServer for setting SSID/PWD(Default 192.168.36.1).<BR>

2.  Modified AT+CWSTARTSMART<BR>
    AT+CWSTARTSMART=#1<BR>

    #1: 1<=Try cnt<=60 (Minutes)<BR>
    If failed to connect via Airkiss, the WizFi360 start WebServer(Default 192.168.36.1).<BR>

    Example:<BR>
    AT+CWSTARTSMART=3 : Try Airkiss 3 times<BR>

    AT+CWSTARTSMART : Unlimited try Airkiss<BR>

    The LED(PB_07) is blinking fast during running Oneshot via Airkiss.<BR>
    The LED(PB_07) is blinking slowly during running Oneshot via WebServer.<BR>
    It prints messages to UART1 like below.<BR>

    AT+CWSTARTSMART=2\r\n<BR>
    \r\n<BR>
    OK\r\n<BR>
    \r\n<BR>
    +CWSTARTSMART:Try:1/2\r\n<BR>
    \r\n<BR>
    +CWSTARTSMART:Try:2/2\r\n<BR>
    \r\n<BR>
    +CWSTARTSMART:WebCfgStart\r\n<BR>

3.  AT+CIUPDATE<BR>
    An OTA URL is changed to http://wizwiki.net/download/WizFi360/O11/WizFi360_SDK.img.<BR>

    If you want to update to Version 1.0.x.x, run AT+CIUPDATE="http://wizwiki.net/download/WizFi360/WizFi360_SDK.img"\r\n

## Released 1.0.7.2<BR>
 20200309<BR>
 For existing project<BR>

1.  Added AT+WIZ_NETCONFIG<BR>
    WebServer for setting SSID/PWD(Default 192.168.36.1).<BR>

2.  Modified AT+CWSTARTSMART<BR>
    AT+CWSTARTSMART=#1,#2<BR>
    #1: 1 : ESP-TOUCH<BR>
    #1: 2 : Airkiss<BR>
    #1: 3 : ESP-TOUCH and Airkiss<BR>

    #2: 1<=Try cnt<=60 (Minutes)<BR>
    If failed to connect via ESP-TOUCH/Airkiss, the WizFi360 start WebServer(Default 192.168.36.1).<BR>

    Example:<BR>
    AT+CWSTARTSMART=2,3 : Try Airkiss 3 times<BR>

    AT+CWSTARTSMART : Unlimited try AT+CWSTARTSMART=3<BR>

    The LED(PB_07) is blinking fast during running Oneshot via ESP-TOUCH/Airkiss.<BR>
    The LED(PB_07) is blinking slowly during running Oneshot via WebServer.<BR>
    It prints messages to UART1 like below.<BR>

    AT+CWSTARTSMART=2\r\n<BR>
    \r\n<BR>
    OK\r\n<BR>
    \r\n<BR>
    +CWSTARTSMART:Try:1/2\r\n<BR>
    \r\n<BR>
    +CWSTARTSMART:Try:2/2\r\n<BR>
    \r\n<BR>
    +CWSTARTSMART:WebCfgStart\r\n<BR>

3.  AT+CIUPDATE<BR>
    An OTA URL is http://wizwiki.net/download/WizFi360/WizFi360_SDK.img.<BR>
    
    If you want to update to Version 1.1.x.x, run AT+CIUPDATE="http://wizwiki.net/download/WizFi360/O11/WizFi360_SDK.img"\r\n

## Released 1.1.0.5<BR>
 20200207<BR>

 When the pin PB13 is low level in booting, the WizFi360 runs to SPI mode.<BR>
 Then you cannot use UART to run AT Command and to receive.<BR><BR>

1.  AT+CIUPDATE<BR>
    An OTA URL is http://wizwiki.net/download/WizFi360/WizFi360_SDK.img.<BR>
    
    If you want to update to Version 1.1.x.x, run AT+CIUPDATE="http://wizwiki.net/download/WizFi360/O11/WizFi360_SDK.img"\r\n
 
 부팅시 PB13이 low level이면 SPI Mode로 실행 됩니다.<BR>
 SPI Mode에서는 UART로 AT Command를 받지 않고 출력도 하지 않습니다.<BR>
 
 
