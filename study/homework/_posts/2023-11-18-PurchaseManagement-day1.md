---
title: "애완동물 판매 사이트"
tag: study_homework
---

### 문제
* 애완동물 판매 사이트
* 고양이, 뱀, 금붕어
* 다른 분처럼 고양이 선택하면 고양이 카테고리에 속하는 애들 몇명 보여주기
* 카테고리를 선택하면 판매중, 판매 완료가 고양이들 특성과 함께 보이게 하기
* 구매된 애들은 판매 완료 떠 있게 하기
* 메인 메소드에는 코드가 최대한 짧게 들어갈 수 있도록 하기

- 가이드라인
    * 구매(c) 장바구니()(b) 종료(x)
    * 1)구매에 들어가면 고양이(c), 뱀(s), 금붕어(f) 선택지가 나옴
    * 선택지를 누르면 고양이 여러 마리의 종류, 이름, 나이, 가격, 판매중 뜨기
    * 장바구니 담기, 뒤로가기, 처음화면으로 나가기 버튼이 있음
    * 장바구니 담기를 누르면 해당 고양이가 장바구니에 넣어지고 판매중이 판매완료로 바뀜
    * 뒤로가기를 누르면 고양이, 뱀, 금붕어 선택지가 나오고
    * 처음화면을 누르면 구매, 장바구니, 계산, 종료 선택지가 나옴
    * 2)장바구니에 들어가면 이제까지 장바구니에 담은 애들의 종류, 이름, 가격이 뜸
    * 구매하기, 뒤로가기 선택지가 있음
    * 구매하기를 누르면 이제까지 고른 애들의 종류, 이름, 가격과 총합계가 뜨고
    * 구매하기를 누르면 장바구니가 비워지면서 처음 선택지로 돌아감
    * 3)종료에 들어가면 프로그램 종료
    
    <br>

    * <클래스>
    * 고양이, 뱀, 금붕어 클래스를 만든다
    * 장바구니 메뉴에서 각자 다른 클래스들을 보여줘야 하므로 부모 클래스를 선언해서 상속받게 함
    * 부모 클래스 공통 필드: 종류, 이름, 가격 메소드: 상세특징 나열
    * 첫번째 선택지를 보여주는 메소드...?흠 선택지들을 보여주는 클래스를 만들자
    * 첫번째 선택지(구매,장바구니,종료 대답 리턴), 두번째 선택지(고양이,뱀,금붕어 대답 리턴), 
    * 세번째 선택지(장바구니 담기, 뒤로가기, 처음화면으로 나가기), 네번째 선택지(어떤 아이를 담을건지 물어보고 답을 받음),
    * 다섯번째 선택지(구매하기, 뒤로가기), 여섯번째(구매하기)
    
    <br>

- 작업현황
    - 부모, 자식 클래스까지만 제작

```java
//부모 클래스

class Pet {
	private String species;
	private String sub_species;
	private String name;
	private int price;
	private boolean forSale;
	
	Pet() {}

	public Pet(String species, String sub_species, String name, int price,boolean forSale) {
		super();
		this.species = species;
		this.sub_species = sub_species;
		this.name = name;
		this.price = price;
		this.forSale = forSale;
	}
	
	void printDetail() {
		System.out.printf("%s\t%s\t%s\t%d\t%b \n",species,sub_species,name,price,forSale);
	}

	public String getSpecies() {
		return species;
	}

	public void setSpecies(String species) {
		this.species = species;
	}

	public String getSub_species() {
		return sub_species;
	}

	public void setSub_species(String sub_species) {
		this.sub_species = sub_species;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public int getPrice() {
		return price;
	}

	public void setPrice(int price) {
		this.price = price;
	}

	public boolean getForSale() {
		return forSale;
	}

	public void setForSale(boolean forSale) {
		this.forSale = forSale;
	}

}
```

```java
//자식 클래스

class Cat extends Pet {
	
	private boolean vaccine;
	
	public Cat() {}

	public Cat(String species, String sub_species, String name, int price, boolean forSale,boolean vaccine) {
		super(species, sub_species, name, price, forSale);
		this.vaccine = vaccine;
	}
	
	public Cat(String[] cat) {
		setSpecies(cat[0]);
		setSub_species(cat[1]);
		setName(cat[2]);
		setPrice(Integer.parseInt(cat[3]));
		setForSale(cat[4].equals("y")?true:false);
		setVaccine(cat[5].equals("y")?true:false);
	}

	public boolean isVaccine() {
		return vaccine;
	}

	public void setVaccine(boolean vaccine) {
		this.vaccine = vaccine;
	}
}


class Snake extends Pet {
	
	private boolean poison;
	
	public Snake() {}

	public Snake(String species, String sub_species, String name, int price, boolean forSale,boolean poison) {
		super(species, sub_species, name, price, forSale);
		this.poison = poison;
	}
	
	public Snake(String[] snake) {
		setSpecies(snake[0]);
		setSub_species(snake[1]);
		setName(snake[2]);
		setPrice(Integer.parseInt(snake[3]));
		setForSale(snake[4].equals("y")?true:false);
		isPoison(snake[5].equals("y")?true:false);
	}

	public boolean isPoison() {
		return poison;
	}

	public void isPoison(boolean poison) {
		this.poison = poison;
	}
}



class Goldfish extends Pet {
	
	private String habitat;
	
	public Goldfish() {}

	public Goldfish(String species, String sub_species, String name, int price, boolean forSale,String habitat) {
		super(species, sub_species, name, price, forSale);
		this.habitat = habitat;
	}
	
	public Goldfish(String[] goldfish) {
		setSpecies(goldfish[0]);
		setSub_species(goldfish[1]);
		setName(goldfish[2]);
		setPrice(Integer.parseInt(goldfish[3]));
		setForSale(goldfish[4].equals("y")?true:false);
		setHabitat(goldfish[5]);
	}

	public String getHabitat() {
		return habitat;
	}

	public void setHabitat(String habitat) {
		this.habitat = habitat;
	}
}
```