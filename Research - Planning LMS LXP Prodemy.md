
### Reference

- https://courselit.app/
- https://openedx.org/
- https://www.learnhouse.app/
- https://classroomio.com/
- https://github.com/instructure/canvas-lms

---
### Research Note

#### Courselit

###### Notes
- self host docker
- perfoma kurang bagus ketika pertama kali akses
	- pindah ke halaman lain kurang cepat
	- tidak ada indikasi loading ketika proses pindah halaman
- penyimpanan static asset menggunakan medialit, self host juga
- tidak redirect ke halaman list data setelah submit form
- ux quiz untuk peserta kurang bagus, harus klik checkboxnya baru kepilih

###### Site Features
- customizable landing page
- blog post
- course list
	- course type
		- free
		- paid
	- preview lesson before buying
	- buy course page
	- launch course
		- divided by section and lesson
		- checklist on completed lesson
###### Dashboard Features
- Payment Gateway Webhook Setting
- Products
	- Product Type
		- Downloadable
		- Courses
	- Product Feature
		- Customizable Page (basic)
		- Pricing
		- Content
			- Section
				- Lesson
					- Text
						- WYSIWYG
					- File
					- Video
					- Audio
					- Pdf
					- Embed
					- Quiz 
						- Multiple Choice - Answer
						- Passing Grade
- Blog
	- Customizable Page (basic)
- Pages
	- Customizable Page (basic)
- Mail
	- marketing email
- User Management

---
#### OpenEDX

###### Note
- self host docker
- instalasi pakai tutor, dan manajemennya pakai tutor cli
- MIT & Harvard standard
- built in feature lumayan kompleks
- aplikasi terbagi jadi 2
	- LMS => tempat belajarnya peserta
	- CMS => tempat guru buat materi
- LMS ada aplikasi mobilenya
- customizable, perlu tau linux + js + python
	- theme
	- xblock (component dalam lesson)
- steep learning curve

###### Features
- LMS & CMS
- reusable content library
- mixed content in one lesson (bisa nyampur text, video dan soal di satu halaman)
- course structure
	- course
		- section
			- subsection
				- unit (lesson)
					- component (content)
- components
	- Components (also known as [XBlocks](http://local.edly.io/xblock/07c8d8e217e04f8ca2f10bbd3cb36980)) are specific learning objects and include, but are not limited to:
		- **Videos**
		- **HTML** (text, images, iframed content)
		- **Basic CAPA Problems** (such as multiple choice or text entry)
		- **Advanced Problems** (such as drag-and-drop problems or Javascript assessments)
		- **Peer- and staff-assessed assignments** (referred to as Open Response Assignments, or ORA)
		- **Third-party XBlocks** (plugin components, such as Polls, Surveys, or integrations with third-party software)
- LMS key features:
	- **The course outline**
	- **The learning sequence**
	- **Learner progress**
	- **The Instructor dashboard**
- 

---
