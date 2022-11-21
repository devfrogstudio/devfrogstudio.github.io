---
title: "Player Prefs 정리"
categories:
  - Unity Features
tag:
  - [Unity, PlayerPrefs]
toc: true
toc_sticky: true
---

# PlayerPrefs로 저장하기

가장 간단한 저장 시스템.

PlayerPrefs는 별도의 암호화 없이 로컬 레지스트리에 저장된다.  
유저의 암호와 같이 중요한 데이터에는 사용하지 말 것.

정수형, 실수형, 문자열 형식만 지원한다.  
이보다 큰 데이터의 경우 이 3가지 데이터로 나눠서 저장해야하는 불편함이 있다.

딕셔너리나 헤쉬맵과 같이 key와 value의 형태로 데이터를 저장한다.

중복된 key와 다른 value를 입력했다면 덮어쓰기로 인해 가장 마지막 value가 저장된다.

<!--Table-->

| <span style="color:red">입력</span> | <span style="color:red">출력</span> |
| ----------------------------------- | ----------------------------------- |
| PlayerPrefs.SetInt                  | PlayerPrefs.GetInt                  |
| PlayerPrefs.SetFloat                | PlayerPrefs.GetFloat                |
| PlayerPrefs.SetString               | PlayerPrefs.GetString               |

### 예시

```cs
public void SaveData()
{
  PlayerPrefs.SetString("Input", inputField.text);
}

public void LoadData()
{
  inputField.text = PlayerPrefs.GetString("Input");
}

public void DeleteData()
{
  PlayerPrefs.DeleteKey("Input");
  PlayerPrefs.DeleteAll();
}
```

---

### 내 생각

- 암호화도 없이 로컬에 저장된다는 점이 쓰기 어렵게 만든다.
- Option이나 Menu와 관련된 데이터를 저장하는 용도로 보인다.
- 빠르게 프로토타이핑 할 때는 사용해도 괜찮겠다.

---

### 참고

공식문서:
https://docs.unity3d.com/ScriptReference/PlayerPrefs.html
