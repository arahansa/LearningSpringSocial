LearningSpringSocial
====================

스프링 소셜+시큐리티+JPA 등등 따라해보자.

아 이상하게 .. ㅡ.ㅡ;; .gitignore 했는데도..;; 프로젝트 설정 파일이 올라간 것같습니다.. 
수동으로 설정 덮어씌워서지워주시길..;(무책임)

블로그글 : http://adunhansa.tistory.com/192

본래 저자 분의 깃허브 : https://github.com/pkainulainen/spring-social-examples/tree/master/sign-in/spring-mvc-normal
---------
** Thanks Petri!!
---------

제 깃허브가 다른 점은 maven 빌드를 안하고 이클립스에서 바로 빌드되게 해놨습니다.;;

수동으로 미리 이런 데이터베이스 환경설정을 해주셔야 할 것입니다~ 

CREATE DATABASE `socialtwitter` /*!40100 DEFAULT CHARACTER SET utf8 */;

CREATE TABLE `userconnection` (
  `userId` varchar(255) NOT NULL,
  `providerId` varchar(255) NOT NULL,
  `providerUserId` varchar(255) NOT NULL,
  `rank` int(11) NOT NULL,
  `displayName` varchar(255) DEFAULT NULL,
  `profileUrl` varchar(512) DEFAULT NULL,
  `imageUrl` varchar(512) DEFAULT NULL,
  `accessToken` varchar(255) NOT NULL,
  `secret` varchar(255) DEFAULT NULL,
  `refreshToken` varchar(255) DEFAULT NULL,
  `expireTime` bigint(20) DEFAULT NULL,
  PRIMARY KEY (`userId`,`providerId`,`providerUserId`),
  UNIQUE KEY `UserConnectionRank` (`userId`,`providerId`,`rank`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
