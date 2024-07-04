# Packet Switching

: transmitted in small packets(user data + ctrl info) "순서, path 다르게 도착"

- 장점:
  
  - line efficiency
  
  - data rate conversion
  
  - 네트워크가 바쁘더라도 packet이 accepted; 큐잉 메커니즘
  
  - priority

- standard: ITU-T

## Switching Techniques

handling packets two ways for packet -> network 

1. Datagram
   : 독립적으로 route되어 이전 packet들을 참조하지 않음
   - no call set-up phase
   - more flexible
   - more reliable
  
2. Virtual Circuit
   : packet을 보내기 전에 established된 preplanned path 따라 순서대로 route함 ≈ circuit switching
   - call setup 필요 -> packet forwarding 속도 향상
   - network can provide sequencing and error control
   - less reliable
     (∵ path를 다 정해놓고 사용하므로 중산의 swithing node가 너무 많이 사용돼서 계속 쌓여서 queue에서 나오지 않을 때 reliable 보장 불가)

## Asynchronous Transfer Mode(ATM)

: packet switching(virtual switching) 구현

- "cells" small, fixed 

  > small: high flexibility
  >
  > fixed: lower jiter

- rich QoS capability를 서포트해주고 traffic을 관리하기 위한 강력한 도구

- WAN의 telecommunication에서 사용

- backbone network technology로써 사용

- ATM -> MPLS로 발전

- circuit switching과 같은 performance, packet switching과 같은 flexibility와 efficiency를 제공하기 위해 설계됨

  > physical = circuit switching: VCC

## Virtual Channel Connection(VCC)

- logical connection in ATM

- virtual circuit과 유사: 연결지향성, 경로설정, 고정된 크기의 셀 전송

- 두 end user간의 set-up 필요

- grouping: VPC

  > 여러개의 VCC를 VPC가 grouping하고 있음
  >
  > 여러개의 VCC를 관리하기 위한 identifier restriction이 VPC내에 필요

  -> simplifying, reliable, short set-up time, performace↑, processing↓
  
