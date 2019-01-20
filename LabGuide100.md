# OCI 콘솔을 이용한 쿠버네티스 클러스터 생성

## Oracle Cloud infrastructure 환경 설정

### **STEP 1**: OCI 대쉬보드 로그인

- 수신한 Trial Welcome 메일을 참조하여 **Username, Password, Cloud Account Name** 참조.

  ![](images/200/0.1.png)

- 사전에 신청한 Trial 계정을 이용해 로그인, Trial 계정이 없는 경우 Workshop Instructor에게 요청

    [https://cloud.oracle.com/en_US/sign-in](https://cloud.oracle.com/en_US/sign-in)

- **Cloud Account Name** 정보 입력하고 **My Services** 버튼 클릭. 

  ![](images/200/1.png)

-  **Username** 과  **Password** 를 입력하고 **Sign In** 클릭. 

  ![](images/200/2.png)


- 대쉬보드의 좌측 상단 **hamburger menu** 클릭

  ![](images/200/3.png)

- **Services** 메뉴 클릭하고 **Compute** 클릭

  ![](images/200/4.png)

- 이렇게 하면 OCI 콘솔 로그인 화면이 나온다. 이는 오라클에는 OCI-Classic 서비스와 OCI 서비스가 있기 때문이로 위와 동일한 계정 정보로 한번 더 로그인 한다. 

  ![](images/200/5.png)

### **STEP 2**: Add a Policy Statement for OKE

  - 쿠버네티스 서비스 생성하기 전에 명시적으로 policy를 추가해야 한다. OCI 메뉴에서 **Identity->Policies** 선택

    ![](images/200/LabGuide200-13c980fa.png)

  - Compartment 드롭다운 메뉴에서 **root compartment**를 선택

    ![](images/200/LabGuide200-a321171a.png)

  -  **PSM-root-policy** 클릭
  
  ![](images/200/LabGuide200-a321171a.png)

  - **Add Policy Statement** 클릭

    ![](images/200/LabGuide200-3d4a7471.png)

  - Statement 박에에, `allow service OKE to manage all-resources in tenancy` 복사해서 입력 하고 **Add Statement** 클릭

    ![](images/200/LabGuide200-bd5bcbd1.png)

### **STEP 3**: OCI 콘솔을 이용한 쿠버네티스 클러스터 생성

  - 이제 쿠버네티스 클러스터를 만들 준비가 됐다. OCI 콘솔 메뉴에서 **Developer Services->Container Clusters (OKE)**를 선택.

    ![](images/200/LabGuide200-5c0a2b4c.png)

  - In the Compartments drop down, select the **Demo** compartment.

    ![](images/200/LabGuide200-4071818d.png)

  - **Create Cluster** 클릭

    ![](images/200/LabGuide200-2e2ab7ca.png)

  - 데모를 간략히 하기 위해 선택된 그대로 Create 버튼을 클릭한다. 

    ![](images/LabGuide200-6ff14524.png)
    ![](images/LabGuide200-11191333.png)

    - 사용자의 필요에 따라 클러스터 설정을 추가로 설정할 수 있다.
    - 현재 2가지 버전의 k8s를 사용가능 v1.11.5, v1.10.11
    - 디폴드 옵션은 클러스터를 위한 VCN(Virtual Cloud Network), 3개의 서브넷과 2개의 로드 밸랜서 그리고 각 서브넷에 Worker Node VM(총 3개) 이 생성된다. 
    - Node Pool에 구성할 Worker Node 설정 가능

  - **Create** 클릭하면 클러스터 디테일 화면이 나온다. 

**[Lab 200으로](LabGuide200.md)**

