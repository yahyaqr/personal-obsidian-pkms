---
created: Friday, November 4th 2022 - 21.06
updated: Friday, November 4th 2022 - 21.06
---
```js
const kuotaMalam = 1700;
const kuotaWeekend = 4000;
const kuotaSiang = 6000;

let kuotaTerkini = (jenisKuota, sisaHari, kuotaTerkini) => {
	let name = 0;
	if (jenisKuota == 6000) {
		name = "Kuota Siang";
	} else if (jenisKuota == 1700) {
		name = "Kuota Malam";
	} else if (jenisKuota == 4000) {
		name = "Kuota Weekend";
	}
	const terpakai = Number(((jenisKuota - kuotaTerkini)/100).toFixed(2));
	const sisa = Number((kuotaTerkini/100).toFixed(2));
	const rerata = Number(((kuotaTerkini/(30-sisaHari))/100).toFixed(2));
	const ideal = Number(((kuotaTerkini/sisaHari)/100).toFixed(2));
	console.log(name);
	console.log("Telah terpakai: " + terpakai + " GB");
	console.log("Sisa kuota: " + sisa + " GB");
	console.log("Rerata pemakaian: " + rerata + " GB");
	console.log("Pemakaian harian ideal: " + ideal + " GB");
	console.log("")
};

const sisaHari = 26;
kuotaTerkini(kuotaMalam, sisaHari, 1279);
kuotaTerkini(kuotaWeekend, sisaHari, 4000);
kuotaTerkini(kuotaSiang, sisaHari, 5390);
```