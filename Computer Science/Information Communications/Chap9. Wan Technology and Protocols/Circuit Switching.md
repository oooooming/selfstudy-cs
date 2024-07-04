# Circuit Switching

: dedicated path "차례대로"

- 문제: inefficient(wasted capacity), set-up time

  -> Circuit Switching Technology 등장

## Circuit Switching Technology

⭐no TX delay & jiter⭐

### blocking / nonblocking

- blocking

  : 모든 path가 다 in use하여 station의 access를 제한함

  -> voice system에 사용됨 (duration이 짧, 동시통화비율 낮)

- nonblocking

  : 모든 station의 access를 허용함

  -> data connection에 사용됨

### Space Division Switching

- signal path physically 완전히 seperated

### Time Division Switching

- 하드웨어 하나로 소프트웨어적으로 문제를 해결함
  
  : physically same circuit, time slot을 다르게 할당하여 switching

  -> virtual cirsuit setup and maintain에 사용됨
