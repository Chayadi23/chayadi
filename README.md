# chayadi
on carosel
import { Swiper, SwiperSlide } from 'swiper/react';
import 'swiper/css';
import 'swiper/css/pagination';
import { Pagination } from 'swiper/modules';
import { Card, CardContent } from "@/components/ui/card";

const tips = [
  { title: "Gunakan Shortcut Keyboard", description: "Pelajari shortcut keyboard untuk meningkatkan produktivitas kerja." },
  { title: "Atur Waktu dengan Teknik Pomodoro", description: "Gunakan teknik Pomodoro untuk meningkatkan fokus dan menghindari kelelahan." },
  { title: "Optimalkan Ruang Kerja", description: "Buat ruang kerja yang nyaman dan bebas dari gangguan untuk hasil yang lebih maksimal." },
  { title: "Gunakan Aplikasi Manajemen Tugas", description: "Aplikasi seperti Trello dan Notion dapat membantu mengorganisir pekerjaan dengan lebih baik." },
  { title: "Jaga Kesehatan dengan Istirahat Teratur", description: "Luangkan waktu untuk istirahat agar tetap produktif sepanjang hari." }
];

export default function TipsCarousel() {
  return (
    <div className="max-w-lg mx-auto py-6">
      <h2 className="text-2xl font-bold text-center mb-4">Tips & Trick</h2>
      <Swiper
        modules={[Pagination]}
        pagination={{ clickable: true }}
        spaceBetween={20}
        slidesPerView={1}
        className="w-full"
      >
        {tips.map((tip, index) => (
          <SwiperSlide key={index}>
            <Card className="p-6 text-center bg-white shadow-lg rounded-2xl">
              <CardContent>
                <h3 className="text-xl font-semibold mb-2">{tip.title}</h3>
                <p className="text-gray-600">{tip.description}</p>
              </CardContent>
            </Card>
          </SwiperSlide>
        ))}
      </Swiper>
    </div>
  );
}

