### /api/user/v1/signup
> 회원가입  

##### Response
- 로그인 성공
    ```json
    {
        "code": 0,
        "data": {
            "refresh_token": <refresh_token>,
            "access_token": <access_token>
        },
        "description": "NORMAL",
        "status": 200
    }
    ```
- 이미 가입된 email
    ```json
    {
        "code": 10002,
        "data": {
            "userid": "dudwo56@gmail.com"
        },
        "description": "ALREADY_EXISTS_USERID",
        "status": 200
    }
    ```
- 입력한 referral_code가 존재하지 않는다.
    ```json
    {
        "code": 10020,
        "description": "NOT_EXISTS_REFERRAL_CODE",
        "status": 200
    }
    ```

---

### /api/user/v1/userid/check
> email 중복 체크  

##### Response
- 정상처리 
    ```json
    {
        "code": 0,
        "data": {
            "available": true
        },
        "description": "NORMAL",
        "status": 200
    }
    ```

---

### /api/user/v1/country/code/list
> 국가 목록(코드)  

##### Response
- 정상처리
    ```json
    {
        "code": 0,
        "data": {
            "country_list": [
                {
                    "country_code": "93",
                    "country_id": 1,
                    "country_name": "Afghanistan"
                },
                ...,
            ]
        },
        "description": "NORMAL",
        "status": 200
    }
    ```

---

### /api/user/v1/country/name/list
> 국가 목록  

##### Response
- 정상처리
    ```json
    {
        "code": 0,
        "data": {
            "country_list": [
                {
                    "country_id": 1,
                    "country_name": "Afghanistan"
                },
                ...,
            ]
        },
        "description": "NORMAL",
        "status": 200
    }
    ```

---

### /api/user/v1/account/freeze
> 계정잠금  

##### Response
- 계정잠금 성공
    ```json
    {
        "code": 0,
        "description": "NORMAL",
        "status": 200
    }
    ```
- userid 확인 불가
    ```json
    {
        "status": 200,
        "code": 10000,
        "description": "NOT_EXISTS_USERID"
    }
    
    ```