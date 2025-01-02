import streamlit as st
from PIL import Image
import os

def convert_to_jpg(image, output_filename):
    # Convert the uploaded image to JPG and save it to the specified filename
    img = Image.open(image)
    output_path = f"{output_filename}.jpg"
    img.convert("RGB").save(output_path, "JPEG")
    return output_path

def main():
    st.title("Image Converter to JPG")
    st.write("Upload your image, and we'll convert it to JPG format for you!")

    # File uploader widget
    uploaded_file = st.file_uploader("Choose an image file", type=["png", "jpeg", "jpg", "bmp", "gif"])

    if uploaded_file is not None:
        # Display the uploaded image
        st.image(uploaded_file, caption="Uploaded Image", use_column_width=True)

        # Convert the uploaded image to JPG
        output_filename = "converted_image"
        output_path = convert_to_jpg(uploaded_file, output_filename)

        # Provide a download button for the converted image
        with open(output_path, "rb") as file:
            st.download_button(
                label="Download JPG Image",
                data=file,
                file_name="converted_image.jpg",
                mime="image/jpeg"
            )

        # Remove the file after use to clean up
        os.remove(output_path)

if __name__ == "__main__":
    main()
