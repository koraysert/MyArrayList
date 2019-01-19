# MyArrayList
package arrayListYapimi.base;

import java.util.List;

public interface ArrayListMetodlar<T>{
	
	public void terscevir();
	public void ekle(T eklenecek);
	public void sil(T silinecek);
	//public int sonindex(T aranan);
	public int ilkindex(T aranan);
	public boolean bul(T aranan);
	public void getir(T index);	
	public void sirala();
	
	

	

}

package arrayListYapimi.base;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

import javaComparator.base.Oyuncu;

public class ArrayListYapimi implements ArrayListMetodlar{
	Object [] dizi;
	public ArrayListYapimi(int boyut) {dizi = new Object[boyut];}
	


	public Object[] getDizi() {
		return dizi;
	}


	public void setDizi(Object[] dizi) {
		this.dizi = dizi;
	}


	@Override
	public void terscevir() {
		// TODO Auto-generated method stub
		Object obj =null;
		for(int i=0;i<dizi.length/2;i++) {obj =dizi[i]; dizi[i]=dizi[dizi.length-i-1];dizi[dizi.length-i-1]=obj;}
		
	}

	@Override
	public void ekle(Object eklenecek) {
		// TODO Auto-generated method stub
		
		for(int i=0;i<dizi.length;i++) {if(dizi[i]==null) {dizi[i]=eklenecek;break;}}
	}

	@Override
	public void sil(Object silinecek) {
		// TODO Auto-generated method stub
		for(int i=0;i<dizi.length;i++) {if(dizi[i]!=null&&dizi[i].equals(silinecek)) {dizi[i]=null;}}
	}



	@Override
	public int ilkindex(Object aranan) {
		// TODO Auto-generated method stub
		int index=0;
		for(int i=0;i<dizi.length;i++) {if(dizi[i]!=null&&dizi[i].equals(aranan)) {index =i;break;}}
		return index;
	}

	@Override
	public boolean bul(Object aranan) {
		// TODO Auto-generated method stub
		boolean durum=false;
		for(int i=0;i<dizi.length;i++) {if(dizi[i]!=null&&dizi[i].equals(aranan)) {durum=true;break;}}

		return durum;
	}



	@Override
	public void getir(Object aranan) {
		// TODO Auto-generated method stub
		System.out.print(getDizi()[(Integer)(aranan)]);
	}

	
	@Override
	public void sirala() {
		// TODO Auto-generated method stub
		int obj =0;
		for (int i = 0; i < dizi.length; i++) {
			for (int j = 0; j < dizi.length; j++) {
				if (dizi[i] !=null && dizi[j] !=null && (Integer)dizi[i] > (Integer)dizi[j]) {
					obj =(Integer) dizi[i];
					dizi[i]=dizi[j];
					dizi[j]=obj;
					j = j - 1;
				}
			}

		}
		System.out.println();
		for (Object tmp : dizi) {
			System.out.println(tmp);
		}
	}



//	@Override
//	public int sonindex(Object aranan) {
//		// TODO Auto-generated method stub
//		return 0;
//	}

	

}
package arrayListYapimi.base;

import java.util.ArrayList;
import java.util.List;

public class Runner {
	
	public static void main(String[] args) {
		
		
	
		
		ArrayListMetodlar alm = new ArrayListYapimi(5);

	
		//////////////////////////////////////////////////
		
	
		
		//alm.ekle(,null);
		alm.ekle(1);
		alm.ekle("b");
		alm.ekle("b");
		alm.ekle('d');
		
		alm.getir(0);
		alm.getir(1);
		alm.getir(2);
		alm.getir(3);
		alm.getir(4);
		
		System.out.print(" ters: ");
		alm.terscevir();
		alm.getir(0);
		alm.getir(1);
		alm.getir(2);
		alm.getir(3);
		alm.getir(4);
		
		System.out.print(" b'ilkindex: "+alm.ilkindex("b"));
		//System.out.print(" b'sonindex: "+alm.sonindex("b"));
		
		alm.sil("b");
		alm.sil("c");
		//alm.sil(liste,1);
		alm.sil('d');
		System.out.print(" silme yapıldı tekrar getiriliyor: ");
		alm.getir(0);
		alm.getir(1);
		alm.getir(2);
		alm.getir(3);
		alm.getir(4);
		
		
		
		System.out.print(" b: "+alm.bul("b"));
		System.out.print(" c: "+alm.bul("c"));
		System.out.print(" 1: "+alm.bul(1));
		System.out.print(" d: "+alm.bul("d"));
		System.out.println();
		//////////////////////////////////////////////////////////


		
		//alm.ekle(,null);
		alm.ekle(1);
		alm.ekle(2);
		alm.ekle(3);
		alm.ekle(4);
		
		
		
		alm.getir(0);
		alm.getir(1);
		alm.getir(2);
		alm.getir(3);
		alm.getir(4);
		
		System.out.print(" ters: ");
		alm.terscevir();
		alm.getir(0);
		alm.getir(1);
		alm.getir(2);
		alm.getir(3);
		alm.getir(4);
		
		System.out.print(" b'ilkindex: "+alm.ilkindex("b"));
		//System.out.print(" b'sonindex: "+alm.sonindex("b"));
		
		alm.sil("b");
		alm.sil("c");
		//alm.sil(int,1);
		alm.sil('d');
		System.out.print(" silme yapıldı tekrar getiriliyor: ");
		alm.getir(0);
		alm.getir(1);
		alm.getir(2);
		alm.getir(3);
		alm.getir(4);
		
		
		
		System.out.print(" 1: "+alm.bul(1));
		System.out.print(" 4: "+alm.bul(4));
		System.out.print(" 0: "+alm.bul(0));
		System.out.print(" 55: "+alm.bul(55));
		
		alm.sirala();
		///////////////////////////////////////////////////////////
		
		
	}

}
