import qrcode
from qrcode.constants import ERROR_CORRECT_H
from PIL import Image
import os

def generate_qr():
    print("\n====== QR CODE GENERATOR ======\n")

    # User Input
    data = input("Enter text or URL: ")

    if not data.strip():
        print("Error: Input cannot be empty!")
        return

    # QR Customization
    print("\nChoose QR Color:")
    print("1. Black")
    print("2. Blue")
    print("3. Green")
    print("4. Red")

    color_choice = input("Enter choice (1-4): ")

    colors = {
        "1": "black",
        "2": "blue",
        "3": "green",
        "4": "red"
    }

    fill_color = colors.get(color_choice, "black")

    # Create QR Object
    qr = qrcode.QRCode(
        version=1,
        error_correction=ERROR_CORRECT_H,
        box_size=12,
        border=4
    )

    qr.add_data(data)
    qr.make(fit=True)

    # Generate QR Image
    img = qr.make_image(fill_color=fill_color, back_color="white")

    # File Name
    file_name = input("\nEnter file name: ").strip()

    if not file_name:
        file_name = "qr_code"

    file_path = f"{file_name}.png"

    # Save Image
    img.save(file_path)

    print(f"\n✅ QR Code saved as '{file_path}'")

    # Open Automatically
    open_choice = input("\nDo you want to open the QR code? (y/n): ").lower()

    if open_choice == "y":
        try:
            Image.open(file_path).show()
        except Exception as e:
            print("Could not open image:", e)

    print("\nThank you for using QR Generator!")

# Main Program
while True:
    generate_qr()

    again = input("\nGenerate another QR Code? (y/n): ").lower()

    if again != "y":
        print("\nProgram Closed.")
        break
