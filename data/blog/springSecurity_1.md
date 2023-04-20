---
title: 'Spring Security - 1'
date: '2023-4-19'
tags: ['Backend', 'Java', 'SpringSecurity', '이론']
draft: false
summary: 'Spring Security 는 Spring 에서 인증과 인가에 대한 처리를 해주는 Framework 로, 먼저 인증/인가에 대한 이해와 다양한 방식을 알 필요가 있다.'
---

# Summary

Spring Security 는 Spring 에서 인증과 인가에 대한 처리를 해주는 Framework 로, 먼저 인증/인가에 대한 이해와 다양한 방식을 알 필요가 있다.

#

# 인증 & 인가

## 인증(Authentication)

보호된 리소스에 접근한 대상에 대해 이 유저가 누구인지, 작업을 수행해도 되는 주체인지 확인하는 과정 → 누구인가?

- **주요 컴포넌트**
  - AuthenticationManager
  - AuthenticationProvider
- **인증되지 않을 시**
  - 401 status code

## 인가(Authorization)

해당 리소스에 대해 접근 가능한 권한을 가지고 있는지 확인하는 과정 → 접근이 가능한가?

- **주요 컴포넌트**
  - AccessDecisionManager
  - AccessDecisionVoter
- **인증되지 않을 시**
  - 403 status code

#

# 프로세스 & 방식

![인증프로세스.png](/static/images/springSecurity_1/1.png)

1. 사용자 ID / Password 입력
2. 인증서버로 요청 / 토큰 발급
3. 인증토큰으로 서비스 접근 / 로그인 허용
4. 발급된 토큰과 함께 응답
5. 이 후, 토큰과 함께 API 호출 / 인가 확인 후 해당 응답
