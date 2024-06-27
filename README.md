import random

def main():
  """
  وظيفة أساسية لتشغيل لعبة تخمين الرقم.
  """

  # تحديد الرقم السري عشوائيًا
  secret_number = random.randint(1, 100)

  # عدد المحاولات
  attempts = 7

  while attempts > 0:
    # استعلام المستخدم عن تخمينه
    try:
      guess = int(input(f"ما هو رقمك المخمّن؟ (لديك {attempts} محاولات متبقية): "))
    except ValueError:
      print("إدخال غير صحيح. يرجى إدخال رقم صحيح.")
      continue

    # تقييم التخمين
    if guess == secret_number:
      print(f"مبروك! لقد نجحت في تخمين الرقم السري!")
      break
    elif guess < secret_number:
      print("رقمك المخمّن أصغر من الرقم السري.")
    else:
      print("رقمك المخمّن أكبر من الرقم السري.")

    attempts -= 1

  # إذا انتهت المحاولات دون تخمين الرقم
  if attempts == 0:
    print(f"للأسف، لقد انتهت محاولاتك. الرقم السري هو {secret_number}.")

if __name__ == "__main__":
  main()
