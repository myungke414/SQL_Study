# SQL_Study
 
 
```
CREATE TABLE STADIUM (    /*           */
STADIUM_ID    CHAR(3) NOT NULL,  /* 고정길이의 스타디움아이디 낫널 */
STADIUM_NAME  VARCHAR(40) NOT NULL, /* 가변길이의 스타디움네임 낫널 */
HOMETEAM_ID   CHAR(3), /* 고정길이의 홈팀아이디 */
SEAT_COUNT    INT, /* 숫자의 싯카운트 */
ADDRESS       VARCHAR(60), /* 가변길이의 주소 */
DDD           VARCHAR(3), /* 가변길이의 DDD */
TEL           VARCHAR(10), /* 가변길이의 TEL */
CONSTRAINT STADIUM_PK PRIMARY KEY (STADIUM_ID) /* 제약조건 스타디움의 기본키는 스타디움아이디 */
);
CREATE TABLE TEAM (
TEAM_ID     CHAR(3) NOT NULL, /* 고정길이의 팀아이디 낫널 */
REGION_NAME VARCHAR(8) NOT NULL, /* 가변길이의 지역이름 낫널 */
TEAM_NAME   VARCHAR(40) NOT NULL, /* 가변길이의 팀이름 낫널 */
E_TEAM_NAME VARCHAR(50), /* 가변길이의 E팀이름 */
ORIG_YYYY   CHAR(4), /* 고정길이의 ORIG_YYYY */
STADIUM_ID  CHAR(3) NOT NULL, /* 고정길이의 스타디움아이디 낫널 */
ZIP_CODE1   CHAR(3), /* 고정길이의 ZIP_CODE1 */
ZIP_CODE2   CHAR(3), /* 고정길이의 ZIP_CODE2 */
ADDRESS     VARCHAR(80), /* 가변길이의 주소 */
DDD         VARCHAR(3), /* 가변길이의 DDD */
TEL         VARCHAR(10), /* 가변길이의 TEL */
FAX         VARCHAR(10), /* 가변길이의 FAX */
HOMEPAGE    VARCHAR(50), /* 가변길이의 홈페이지 */
OWNER       VARCHAR(10), /* 가변길이의 OWNER */
CONSTRAINT TEAM_PK PRIMARY KEY (TEAM_ID), /* 제약조건 팀의 기본키는 팀아이디 */
CONSTRAINT TEAM_FK FOREIGN KEY (STADIUM_ID) REFERENCES STADIUM(STADIUM_ID) /* 제약조건 스타디움의 기본키인 스타디움 아이디의 외래키인 팀의 스타디움 아이디 */
);
CREATE TABLE SCHEDULE (
STADIUM_ID   CHAR(3) NOT NULL, /* 고정길이의 스타디움아이디 낫널 */
SCHE_DATE    CHAR(8) NOT NULL, /* 고정길이의 SCHE_DATE 낫널 */
GUBUN        CHAR(1) NOT NULL, /* 고정길이의 GUBUN 낫널 */
HOMETEAM_ID  CHAR(3) NOT NULL, /* 고정길이의 홈팀아이디 낫널 */
AWAYTEAM_ID  CHAR(3) NOT NULL, /* 고정길이의 AWAYTEAM_ID 낫널 */
HOME_SCORE   INT(2), /* 숫자의 HOME_SCORE */
AWAY_SCORE   INT(2), /* 숫자의 AWAY_SCORE */
CONSTRAINT SCHEDULE_PK PRIMARY KEY (STADIUM_ID, SCHE_DATE), /* 제약조건 SCHEDULE의 기본키는 STADIUM_ID, SHCE_DATE */
CONSTRAINT SCHEDULE_FK FOREIGN KEY (STADIUM_ID) REFERENCES STADIUM(STADIUM_ID) /* 제약조건 스타디움의 기본키인 STADIUM_ID는 SCHEDULE의 외래키 */
);

CREATE TABLE  PLAYER (
PLAYER_ID     CHAR(7) NOT NULL, /* 고정길이의 PLAYER_ID는 낫널 */
PLAYER_NAME   VARCHAR(20) NOT NULL, /* 가변길이의 PLAYER_NAME은 낫널 */
TEAM_ID       CHAR(3) NOT NULL, /* 고정길이의 TEAM_ID는 낫널 */
E_PLAYER_NAME VARCHAR(40), /* 가변길이의 E_PLAYER_NAME */
NICKNAME      VARCHAR(30), /* 가변길이의 NICKNAME */
JOIN_YYYY     CHAR(4), /* 고정길이의 JOIN_YYYY */
POSITION      VARCHAR(10), /* 가변길이의 POSITION */
BACK_NO       INT(2), /* 숫자의 BACK_NO */
NATION        VARCHAR(20), /* 가변길이의 NATION */
BIRTH_DATE    DATE, /* 날짜의 BIRTH_DATE */
SOLAR         CHAR(1), /* 고정길이의 SOLAR */
HEIGHT        INT(3), /* 숫자의 HEIGHT */
WEIGHT        INT(3), /* 숫자의 WEIGHT */
CONSTRAINT PLAYER_PK PRIMARY KEY (PLAYER_ID), /* 제약조건 PLAYER의 PLAYER_ID는 기본키 */
CONSTRAINT PLAYER_FK FOREIGN KEY (TEAM_ID) REFERENCES TEAM(TEAM_ID) /* 제약조건 TEAM의 기본키인 TEAM_ID는 PLAYER의 외래키인 TEAM_ID */
);


COMMIT;

```
