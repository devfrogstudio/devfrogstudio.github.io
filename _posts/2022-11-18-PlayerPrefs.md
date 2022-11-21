---
title: "Player Prefs 정리"
categories:
  - Unity Features
tag:
  - [Unity, PlayerPrefs]
toc: true
toc_sticky: true
---

## PlayerPrefs로 저장하기

PlayerPrefs는 별도의 암호화 없이 로컬 레지스트리에 저장됩니다.
유저의 암호 같이 중요한 데이터는 PlayerPrefs를 사용하지 마세요.

```cs
int SaveData = PlayerPrefs.GetInt("Save");
Debug.Log(SaveData);
PlayerPrefs.SetInt("Save", 10);
```

Key : 저장된 데이터의 고유값 / 문자열 (String) 형식
Value : 저장된 데이터 / 정수, 실수, 문자열 형식

PlayerPrefs.GetInt : 정수형
PlayerPrefs.GetFloat : 실수형
PlayerPrefs.GetString : 문자열

PlayerPrefs.SetInt
PlayerPrefs.SetFloat
PlayerPrefs.SetString
