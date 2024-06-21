# IP Address Information
---

windows এ আপনি আপনার IP Address বের করতে command prompt থেকে লিখুনঃ ```ipconfig```
linux কম্পিউটারে আপনি আপনার IP Address বের করতে terminal থেকে লিখুনঃ ```ifconfig```

IP Address এর উদাহরণঃ ```192.168.0.1``` এখানে ৩ সংখ্যা বিশিষ্ট সংখ্যার পরে পরে একটি ডট (.) দেয়া আছে।
এছাড়াও, IP Address এর পরে আবার Subnet Mask এবং Default Gateway থাকে।
আপনার প্রতিটি device এ যে ip address থাকে সেগুলো আপনার router আপনার device কে ব্যবহার করতে দেয়। আর, router এর যে সিস্টেম ip address কে ব্যবহার করতে দেয়, সেই সিস্টেম এর নাম হলোঃ DHCP.
ip address দুই ধরণের হতে পারে। যথাঃ IPV4 এবং IPV6 address. প্রতিটি ip address(v4) হলে, দেখতে অনেকটা `192.168.1.2` এই রকম হতে পারে। এই খানে যে ৩ অংক বিশিষ্ট যে সংখ্যা আছে সেগুলো octal number system অনুযায়ী হিসাব করা হয়ে থাকে। এই কারণে এই ৩ অংক বিশিষ্ট সংখ্যা শূন্য (০) থেকে দুইশত পঞ্চান্ন (২৫৫) পর্যন্ত হতে পারে। তাহলে, আমরা বলতে পারি আমাদের ip address এর চেহারা দেখতে `0-255 . 0-255 . 0-255 . 0-255` এই রকম হতে পারে।
প্রতিটি ip address কেই একটি নির্দিষ্ট নিয়মে ভাগ করা যায়। একে বলা হয়, netowrk part এবং host part. 
আপনার নেটওয়ার্কে দুইটি ip address কে আপনি কখনই নিজের জন্য ব্যবহার করতে পারবেন না। তার মধ্যে প্রথম ip address টি। `192.168.1.0` - কারণঃ শুরুর ip address টি network ip address এবং অন্যটি হলোঃ `192.168.1.255` - শেষের ip address. শেষের ip address টিকে বলা হয়ঃ brodcast ip address.

প্রথম্ন যখন internet শুরু হয়, তখন যারা networking এর কাজ করেছেন, তারা ip address কে চার ভাগে ভাগ করেন। যেমন এখনও দেখা যাচ্ছেঃ `0-255 . 0-255 . 0-255 . 0-255` অর্থ্যাত প্রতিটি ভাগে শূন্য থেকে দুইশন পঞ্চান্ন পর্যন্ত ip address রাখা যাবে। মানে প্রতিটি ঘরে ২৫৬ টি করে ip address রাখা যাচ্ছে। তাহলে, total ip address দাঁড়াচ্ছেঃ 2^32 = 4,294,967,296 টি ip address.
সমস্ত ip address কে বেশ কয়েকটি ভাগে ভাগ করে দেয়া হয়। চার্টটি দেখতে হবেঃ

| Class | IP Range | Default Subnet Mask |
| --- | --- | --- |
| A | `1.0.0.0` - `126.255.255.255`| `255.0.0.0` |
| B | `128.0.0.0` - `191.255.0.0`| `255.255.0.0` |
| C | `192.0.0.0` - `223.255.255.0`| `255.255.255.0` |
| D | `224.0.0.0` - `239.255.255.255`| multi-cast |
| E | `240.0.0.0` - `255.255.255.255`| experimental |

এই চার্টে দেখানো নিয়ম অনুযায়ী প্রত্যেকটি ip address এর পাশাপাশি তাদের subnet mask ও দেয়া হয়। এই subnet mask এর দিকে তাকালে দেখা যায়, A Class IP Address এর Default Subnet Mask হয় `255.0.0.0`। এর অর্থ হলোঃ যদি কোনো ip address এর subnet mask হিসেবে default subnet mask ব্যবহার করা হয়, তাহলে, subnet mask এর যেই ঘরগুলোতে `0` দেয়া আছে, সেই ঘর গুলোতে চাইলে, ip address assign করা যায়।
যেমনঃ যদি `10.20.1.12` ip address কাওকে দেয়া হয়, এবং তার default subnet mask হিসেবে, `255.0.0.0` দেয়া হয়, তাহলে, সে তার একটি ip address কে ভাগ করে করে subnet এর প্রতিটি শূন্য এর যায়গায় ২৫৫ পর্যন্ত ভাগ করে নিয়ে, প্রতিটির জন্য ip address assign করতে পারে। যদি `255.0.10.2` এই রকম ব্যবহার করে থাকে, তাহলে সেইটাকে বলে, classless ip. 

IANA(Internet Assigned Numbers Authority) is the authority that gives/assigns IP addresses.
