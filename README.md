# SQL_Study
 
 
```
CREATE TABLE STADIUM (    /*           */
STADIUM_ID    CHAR(3) NOT NULL,  
STADIUM_NAME  VARCHAR(40) NOT NULL,
HOMETEAM_ID   CHAR(3),
SEAT_COUNT    INT,
ADDRESS       VARCHAR(60),
DDD           VARCHAR(3),
TEL           VARCHAR(10),
CONSTRAINT STADIUM_PK PRIMARY KEY (STADIUM_ID)
);
CREATE TABLE TEAM (
TEAM_ID     CHAR(3) NOT NULL,
REGION_NAME VARCHAR(8) NOT NULL,
TEAM_NAME   VARCHAR(40) NOT NULL,
E_TEAM_NAME VARCHAR(50),
ORIG_YYYY   CHAR(4),
STADIUM_ID  CHAR(3) NOT NULL,
ZIP_CODE1   CHAR(3),
ZIP_CODE2   CHAR(3),
ADDRESS     VARCHAR(80),
DDD         VARCHAR(3),
TEL         VARCHAR(10),
FAX         VARCHAR(10),
HOMEPAGE    VARCHAR(50),
OWNER       VARCHAR(10),
CONSTRAINT TEAM_PK PRIMARY KEY (TEAM_ID),
CONSTRAINT TEAM_FK FOREIGN KEY (STADIUM_ID) REFERENCES STADIUM(STADIUM_ID)
);
CREATE TABLE SCHEDULE (
STADIUM_ID   CHAR(3) NOT NULL,
SCHE_DATE    CHAR(8) NOT NULL,
GUBUN        CHAR(1) NOT NULL,
HOMETEAM_ID  CHAR(3) NOT NULL,
AWAYTEAM_ID  CHAR(3) NOT NULL,
HOME_SCORE   INT(2),
AWAY_SCORE   INT(2),
CONSTRAINT SCHEDULE_PK PRIMARY KEY (STADIUM_ID, SCHE_DATE),
CONSTRAINT SCHEDULE_FK FOREIGN KEY (STADIUM_ID) REFERENCES STADIUM(STADIUM_ID)
);

CREATE TABLE  PLAYER (
PLAYER_ID     CHAR(7) NOT NULL,
PLAYER_NAME   VARCHAR(20) NOT NULL,
TEAM_ID       CHAR(3) NOT NULL,
E_PLAYER_NAME VARCHAR(40),
NICKNAME      VARCHAR(30),
JOIN_YYYY     CHAR(4),
POSITION      VARCHAR(10),
BACK_NO       INT(2),
NATION        VARCHAR(20),
BIRTH_DATE    DATE,
SOLAR         CHAR(1),
HEIGHT        INT(3),
WEIGHT        INT(3),
CONSTRAINT PLAYER_PK PRIMARY KEY (PLAYER_ID),
CONSTRAINT PLAYER_FK FOREIGN KEY (TEAM_ID) REFERENCES TEAM(TEAM_ID)
);


COMMIT;

```
