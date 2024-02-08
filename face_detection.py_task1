import cv2
import face_recognition
import os

def recognize_faces(image_path):
    # Load the image
    img = cv2.imread(image_path)

    # Find all face locations and face encodings in the image
    face_locations = face_recognition.face_locations(img)
    face_encodings = face_recognition.face_encodings(img, face_locations)

    # Database of known faces and their corresponding names
    known_face_encodings = []
    known_face_names = []

    # Add your known faces and names to the database
    # For example:
    # known_face_encodings.append(some_face_encoding)
    # known_face_names.append("Name1")

    # Loop through each face found in the image
    for (top, right, bottom, left), face_encoding in zip(face_locations, face_encodings):
        # Check if the face matches any known faces
        matches = face_recognition.compare_faces(known_face_encodings, face_encoding)

        name = "Image 1"  # Default name if no match is found

        # If a match is found, use the name from the known faces database
        if True in matches:
            first_match_index = matches.index(True)
            name = known_face_names[first_match_index]

        # Draw rectangles and display the name
        cv2.rectangle(img, (left, top), (right, bottom), (255, 0, 0), 2)
        font = cv2.FONT_HERSHEY_DUPLEX
        cv2.putText(img, name, (left + 6, bottom - 6), font, 0.5, (255, 255, 255), 1)

    # Display the result
    cv2.imshow('Detected Faces',img)
    cv2.waitKey(0)
    cv2.destroyAllWindows()

if __name__ == "__main__":
    # Path to your testing images
    testing_folder = 'D:/Image testing/Image 1/'  # Update this path

    # Iterate through images in the testing folder
    for image_file in os.listdir(testing_folder):
        image_path = os.path.join(testing_folder, image_file)

        # Perform face recognition on each image
        recognize_faces(image_path)
