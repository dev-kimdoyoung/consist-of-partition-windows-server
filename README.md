# consist-of-partition-windows-server
Terraform과 Ansible을 연동하여 AWS에 Windows Server 생성 및 유저/디스크 구성

## 작업환경
- 앤서블 코어 서버: MAC OS
- 구축/구성 서버: Winmdows Server 2016 Standard

## 목적
### Terraform
- AWS에 구축된 서버 리소스를 테라폼 코드로 관리
- GUI가 아닌, Terraform 코드로 리소스 구축/삭제 등의 작업을 수행함으로써 휴먼 에러를 방지

### Ansible
- 기존 및 신규 Windows Server에 구성할 계정 정보를 앤서블 코드로 관리
- 서버에 직접 접속하여 계정 관리를 하는 것이 아닌, 앤서블 코드로 관리함으로써 휴먼 에러를 방지

## 구현 현황
### Terraform
- [x] AWS provider 등록 및 작업환경 구성
- [ ] module 파일 작성 (modules)
- [ ] 방화벽 (Security Group) 구성
- [ ] 입력 변수 구성 (vars.tf)
- [ ] 출력 변수 구성 (output.tf)
- [ ] EC2 구성 (ec2.tf)

### Ansible
- [x] Ansible Role 생성 및 작업환경 구성
- [x] 신규 유저 생성 및 업데이트 (기존 유저 삭제)
- [x] 디스크 구성
- [ ] 인벤토리 작성

## 사용법(인터넷망 - 업데이트 중)
```bash
$ pwd
consist-of-partition-windows-server/ansible
$ ansible-playbook -i inventory.INI main.yml -vvv
```

```bash
$ tree
.
├── LICENSE
├── README.md
├── manage_partition
│   ├── README.md
│   ├── meta
│   │   └── main.yml
│   ├── tasks
│   │   └── main.yml
│   ├── tests
│   │   ├── inventory
│   │   └── test.yml
│   └── vars
│       └── main.yml
└── manage_user_group
    ├── README.md
    ├── meta
    │   └── main.yml
    ├── tasks
    │   └── main.yml
    └── vars
        └── main.yml

9 directories, 12 files
```
## 작성자
dev-kimdoyoung@github.com

