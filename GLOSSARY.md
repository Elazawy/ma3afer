# Ma3afer (معافر)

An Egyptian online learning marketplace for the General Secondary Stage (الثانوية العامة), where independent teachers publish recorded lessons and students purchase access per lecture or package.

## Language

### Academic Catalog

**Grade** (الصف الدراسي):
One of the three years of Egyptian General Secondary education (1st, 2nd, or 3rd Secondary).
_Avoid_: Year, Level, Class

**Track** (الشعبة / النظام):
An academic specialization or system within a Grade (e.g., Scientific Sciences / علمي علوم, Scientific Math / علمي رياضة, Literary / أدبي, or the Baccalaureate system).
_Avoid_: Branch, Stream, Division

**Subject** (المادة):
An academic discipline taught in Egyptian General Secondary education (e.g., Physics, Chemistry, Arabic).
_Avoid_: Topic, Discipline

**Subject Offering** (مقرر المادة):
The pairing of a Subject with a specific Grade and Track that defines which subjects students in that track study.
_Avoid_: Curriculum mapping, Subject assignment

**Academic Year** (العام الدراسي):
A school year cycle (e.g., 2026/2027) to which a Course and its default access expiry belong.
_Avoid_: Term, Semester, Cohort

### Users & Roles

**Student** (طالب):
A learner enrolled in an Egyptian secondary Grade and Track who browses teachers, tops up a Wallet, and studies purchased content.
_Avoid_: Learner, Customer, User, Buyer

**Teacher** (معلم / مستر):
An approved educator on the platform who owns Courses, sets prices, answers student questions, and earns revenue from sales.
_Avoid_: Instructor, Tutor, Creator, Author

**Admin** (مسؤول):
A platform operator who reviews teacher applications and courses, manages the catalog, handles refunds, payouts, recharge codes, and device resets.
_Avoid_: Staff, Moderator, Operator

**Teacher Application** (طلب انضمام معلم):
A candidate teacher's submission (identity details, requested subjects/grades, experience, phone, and sample video) reviewed by an Admin before they can teach on the platform.
_Avoid_: Onboarding request, Registration form

**Teaching Permission** (صلاحية تدريس):
An Admin-granted authorization allowing a specific Teacher to create Courses for one Subject and Grade combination.
_Avoid_: Qualification, Subject approval, License

### Content & Learning

**Course** (كورس / دورة):
A Teacher's structured offering for one Subject, Grade/Track, and Academic Year.
_Avoid_: Class, Program, Subject page

**Section** (وحدة / فصل):
An ordered grouping of Lectures inside a Course, typically mirroring a curriculum unit or chapter.
_Avoid_: Module, Chapter, Unit

**Lecture** (محاضرة):
The primary purchasable and studyable learning unit inside a Section, containing one or more ordered Lecture Items.
_Avoid_: Lesson, Session, Episode, Video

**Lecture Item** (عنصر المحاضرة):
A single piece of ordered content inside a Lecture: a Video, a PDF Attachment, or a Quiz.
_Avoid_: Material, Asset, Resource

**Free Preview** (محاضرة مجانية / معاينة):
A Lecture explicitly flagged as free so any visitor can watch it without purchasing or verifying a phone number.
_Avoid_: Trial, Sample, Zero-price lecture

**Quiz** (اختبار / امتحان):
An auto-graded assessment attached to a Lecture consisting of single-choice MCQ and True/False questions, optionally supporting images, math formulas, time limits, and shuffling.
_Avoid_: Exam, Test, Assessment

**Quiz Gate** (شرط اجتياز الاختبار):
An optional Teacher-configured rule requiring a Student to pass a Lecture's Quiz before the next Lecture in sequence unlocks.
_Avoid_: Prerequisite lock, Passing barrier

**Lecture Q&A** (أسئلة المحاضرة):
Questions posted by enrolled Students on a Lecture and answered exclusively by the Lecture's Teacher, visible to all Students enrolled in that Lecture.
_Avoid_: Comments, Forum, Discussion, Chat

### Commerce & Codes

**Package** (باقة):
A Teacher-defined bundle of specific Lectures within a Course sold at a single price, commonly organized by calendar month (e.g., "باقة شهر نوفمبر").
_Avoid_: Subscription, Monthly plan, Bundle

**Wallet** (المحفظة):
A Student's internal prepaid EGP balance on the platform from which all Purchases are paid.
_Avoid_: Account balance, Credit, Deposit

**Top-Up** (شحن المحفظة):
An operation that adds EGP funds to a Student's Wallet, either through an online payment gateway or by redeeming a Recharge Code.
_Avoid_: Deposit, Charge, Payment

**Purchase** (عملية شراء):
The atomic acquisition of a single Lecture or a Package by a Student, paid immediately from their Wallet.
_Avoid_: Order, Checkout, Enrollment

**Entitlement** (صلاحية الوصول):
A Student's active right to access a specific Lecture or Package, subject to access expiry and per-video view limits.
_Avoid_: Enrollment, Access grant, Ownership

**Recharge Code** (كود شحن):
An Admin-generated single-use prepaid code that credits a fixed EGP amount to a Student's Wallet upon redemption; batches may optionally be tagged to a Teacher to track offline sales.
_Avoid_: Voucher, Gift card, Top-up pin

**Content Code** (كود محاضرة / كود باقة):
A Teacher-generated single-use code that directly grants an Entitlement to a specific Lecture or Package without using the Student's Wallet; the platform's commission is charged to the Teacher when the batch is generated.
_Avoid_: Access code, Coupon, Promo code, Unlock key

### Ledger & Payouts

**Ledger Account** (حساب دفتري):
A named accounting bucket whose balance is derived solely from its Ledger Entries (e.g., a Student's Wallet, a Teacher's pending or available earnings, platform revenue, or code liability).
_Avoid_: Balance column, Wallet row

**Ledger Transaction** (قيد محاسبي):
An immutable, balanced set of Ledger Entries recording a single financial event (top-up, purchase, commission, refund, or payout).
_Avoid_: Payment record, Financial log

**Platform Commission** (عمولة المنصة):
The percentage share of a sale retained by Ma3afer, defaulting to a global rate with optional per-Teacher overrides and captured permanently on each Purchase.
_Avoid_: Fee, Cut, Revenue share

**Earning** (أرباح المعلم):
A Teacher's net share of a sale after Platform Commission, held as pending during the refund window before becoming available for withdrawal.
_Avoid_: Income, Revenue, Balance

**Payout Request** (طلب سحب أرباح):
A Teacher's request to withdraw available Earnings above the minimum threshold, fulfilled manually by an Admin via bank transfer, InstaPay, or mobile wallet.
_Avoid_: Withdrawal, Settlement, Disbursement

**Refund** (استرداد):
An Admin-executed reversal of a Purchase within the eligibility window that credits the Student's Wallet, reverses the Teacher's pending Earning, and revokes the Entitlement.
_Avoid_: Chargeback, Cancellation, Return

### Access & Anti-Piracy

**Verified Phone** (رقم هاتف موثّق):
A Student's Egyptian mobile number confirmed via OTP before their first financial action, uniquely tied to one account and displayed in the video watermark.
_Avoid_: Contact number, Unverified phone

**Registered Device** (جهاز مسجّل):
One of the bounded client devices (up to two) authorized to hold an active session for a Student account.
_Avoid_: Session, Browser, Login

**Playback Session** (جلسة مشاهدة):
An active video viewing lease for a Student; only one may be active per account at any moment across all Registered Devices.
_Avoid_: Stream, Watch session, Player instance

**View Count** (عداد المشاهدات):
The number of full views a Student has consumed for a specific Video against its configured view limit, incremented once the Student watches past the completion threshold.
_Avoid_: Play count, Impressions, Opens
