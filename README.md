# MySNS

1) 프로젝트 소개
- 사진을 포함한 컨텐츠를 게시할 수 있는 SNS

2) 프로젝트 목표
- 적어도 네이버 블로그의 최소 기능만큼은 구현하는 것
- 할 수 있다면 배포까지 해보는 것
- 포기하지 않고 끝까지 마무리하는 것

3) 기술 스택
- Spring Boot
- JAVA 22.0.2 - LTS 버전 사용 권장 (JAVA 17)
- Apache Tomcat
- MySQL

4) ERD
![image](https://github.com/user-attachments/assets/ced76cb3-390a-47ad-8a74-4f70859c1f07)
// Docs: https://dbml.dbdiagram.io/docs
Table follows {
  follows_id integer [primary key]
  users_id integer
  following_users_id integer
  // followed_users_id integer
  // created_at timestamp
  created_at timestamp
  created_by varchar
  updated_at timestamp
  updated_by varchar
}

Table users {
  users_id integer [primary key]
  users_username varchar
  users_password varchar
  users_name varchar
  users_phone varchar
  users_email varchar
  created_at timestamp
  created_by varchar
  updated_at timestamp
  updated_by varchar
}

Table posts {
  posts_id integer [primary key]
  users_id integer
  posts_title varchar
  posts_content text
  posts_private_flag varchar // or integer
  created_at timestamp
  created_by varchar
  updated_at timestamp
  updated_by varchar
}

Table comments {
  comments_id integer [primary key]
  posts_id integer [primary key]
  users_id integer
  comments_content varchar
  comments_depth integer // 대댓글 구글링 필요
  created_at timestamp
  created_by varchar
  updated_at timestamp
  updated_by varchar
}
