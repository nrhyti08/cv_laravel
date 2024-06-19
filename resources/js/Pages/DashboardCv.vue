<template>
  <div class="cv-container">
    <!-- Bagian Header -->
    <header class="header">
      <h1>{{ name }}</h1>
      <h2>{{ title }}</h2>
    </header>

    <!-- Bagian Tentang Saya -->
    <section class="about">
      <h3>Tentang Saya</h3>
      <p>{{ description }}</p>
    </section>

    <!-- Bagian Pendidikan -->
    <section class="education">
      <h3>Pendidikan</h3>
      <div v-for="edu in education" :key="edu.id" class="resume-item">
        <h4>{{ edu.institution }}</h4>
        <h6><em>{{ edu.degree }}</em></h6>
        <h5>{{ edu.duration }}</h5>
        <ul>
          <li v-for="(achievement, index) in edu.achievements" :key="index">{{ achievement }}</li>
        </ul>
      </div>
    </section>

    <!-- Bagian Pengalaman Kerja -->
    <section class="experience">
      <h3>Pengalaman Kerja</h3>
      <div v-for="exp in experiences" :key="exp.id" class="resume-item">
        <h4>{{ exp.position }}</h4>
        <h6><em>{{ exp.employer }}</em></h6>
        <h5>{{ exp.duration }}</h5>
        <ul>
          <li v-for="(responsibility, index) in exp.responsibilities" :key="index">{{ responsibility }}</li>
        </ul>
      </div>
    </section>

    <!-- Bagian Kontak -->
    <section class="contact">
      <h3>Kontak</h3>
      <ul>
        <li><font-awesome-icon icon="phone" /> {{ phone }}</li>
        <li><font-awesome-icon icon="envelope" /> {{ email }}</li>
        <li><font-awesome-icon icon="map-marker-alt" /> {{ address }}</li>
      </ul>
    </section>
  </div>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { library } from '@fortawesome/fontawesome-svg-core';
import { faPhone, faEnvelope, faMapMarkerAlt } from '@fortawesome/free-solid-svg-icons';

library.add(faPhone, faEnvelope, faMapMarkerAlt);

export default {
  name: 'CV',
  components: {
    FontAwesomeIcon
  },
  data() {
    return {
      name: 'NURHAYATI',
      title: 'Mahasiswa',
      description: 'Mahasiswa semester akhir Diploma 3 Jurusan Manajemen Informatika, pribadi yang menyukai hal yang berhubungan dengan administrasi, penginputan, dan pengolahan data. Familiar dengan berbagai software terutama Microsoft Office dan aplikasi lain dalam bidang administrasi Saya memiliki ketertarikan untuk berkarir di bidang administrasi. Dengan latar belakang pendidikan dan kemampuan yang saya miliki, saya siap menyumbangkan waktu dan kompetensi yang saya miliki.',
      education: [
        { 
          id: 1, 
          degree: 'SMK Negeri 2 Purwakarta', 
          institution: 'Rekayasa Perangkat Lunak', 
          duration: '2018 - 2021', 
          achievements: [
            'Lulus Ujian Kompetisi Keahlian Rekayasa Perangkat Lunak dengan nilai rata-rata 92.',
            'Aktif mengikuti ekstrakurikuler Seni Tari Tradisional.',
            'Berhasil membuat Aplikasi berbasis Desktop "Pembayaran SPP" menggunakan Java Netbeans.',
            'Berhasil membuat website informasi mengenai COVID-19 menggunakan Framework Laravel.',
            'Berhasil membuat Aplikasi berbasis Desktop "Pembayaran Kasir Jelly Potter" menggunakan Java Netbeans.'
          ]
        },
        { 
          id: 2, 
          degree: 'AMIK YPAT Purwakarta', 
          institution: 'Manajemen Informatika', 
          duration: '2021 - Sekarang', 
          achievements: [
            'Anggota Badan Eksekutif Mahasiswa dengan jabatan Menteri Keuangan Periode Tahun 2022-2023.',
            'Aktif mengikuti UKM Seni Tari Tradisional dan UKM Kewirausahaan.',
            'Mengikuti lomba seni tari tradisional tingkat Jawa Barat.'
          ]
        }
      ],
      experiences: [
        { 
          id: 1,
          position: 'Magang - Staff Data Entry', 
          employer: 'BPJS Ketenagakerjaan', 
          duration: 'Februari 2023 - Sekarang',
          responsibilities: [
            'Berkontribusi dalam kelancaran operasional administrasi perusahaan lewat input dan integrasi data tepat waktu.',
            'Mempersiapkan dan menyortir dokumen yang akan digunakan dalam proses input data.',
            'Memastikan akurasi data.',
            'Memelihara area kerja untuk memastikan keselamatan, kebersihan dan nihil kecelakaan kerja.',
            'Memilah dan mengatur kembali dokumen setelah proses input data.'
          ]
        },
        { 
          id: 2,
          position: 'Operator Produksi', 
          employer: 'PT. Xin Cheng Da', 
          duration: 'Oktober - Desember 2022',
          responsibilities: [
            'Menjaga kebersihan dan keteraturan di area produksi.',
            'Melakukan pemeliharaan mesin produksi saat diperlukan.',
            'Memeriksa kualitas produk yang dihasilkan sesuai dengan standar yang telah ditetapkan.',
            'Mengikuti prosedur keselamatan kerja dan menggunakan alat pelindung diri dengan benar.',
            'Melakukan pengukuran dan pengujian produk secara berkala untuk memastikan kualitas produk yang dihasilkan.',
            'Mengoperasikan mesin produksi dengan jenis mesin sesuai dengan standar operasional yang ada.'
          ]
        }
      ],
      phone: '089625803219',
      email: 'nurhyti0208@gmail.com',
      address: 'Jl. Raya Bungursari, Purwakarta, Jawa Barat'
    };
  }
};
</script>

<style scoped>
.cv-container {
  max-width: 1100px;
  margin: 0 auto;
  font-family: Cooper-Black, sans-serif;
}

.header {
  text-align: center;
  padding: 20px;
  background-color: #333;
  color: #fff;
}

.header h1 {
  font-size: 1.5rem;
}

.about, .education, .experience, .contact {
  padding: 20px;
  margin-bottom: 30px;
  background-color: #f4f4f4;
}

.about p {
  text-align: justify; 
}

.about h3, .education h3, .experience h3, .contact h3 {
  font-weight: bold; 
  font-size: 1.1rem;
}

.resume-item {
  margin-bottom: 20px;
}

.resume-item h4 {
  margin-bottom: 5px;
}

.resume-item h6 {
  font-style: italic;
  margin-bottom: 5px;
}

.resume-item h5 {
  font-weight: normal;
  margin-bottom: 10px;
}

.resume-item ul {
  padding-left: 20px;
}

.resume-item ul li {
  list-style-type: disc;
  margin-bottom: 5px;
}

.contact ul {
  list-style-type: none;
  padding: 0;
}

.contact li {
  margin: 10px 0;
  display: flex;
  align-items: center;
}

.contact li svg {
  margin-right: 10px;
}
</style>
