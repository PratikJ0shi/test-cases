# File Upload & Download - Test Cases

This document outlines detailed test cases designed to validate the functionality, performance, and error handling of file upload and download features in a web application. These tests are essential to ensure that files can be uploaded and downloaded correctly, regardless of file type, size, or device.

**Key Testing Focus Areas:**
- **File Upload:** Verifying the handling of different file types, sizes, formats, and edge cases like empty or broken files.
- **File Download:** Ensuring smooth and error-free downloads, including support for various browsers and devices.
- **User Experience:** Ensuring ease of use when uploading or downloading files, including drag-and-drop, progress bars, and preview features.
- **Error Handling:** Testing for appropriate error messages when unsupported formats are uploaded, file size limits are exceeded, or file download links are broken.

The following test cases cover a wide range of scenarios to validate both the technical and user-facing aspects of file upload/download functionalities, ensuring a robust and seamless experience for the end user.

---

| TC ID | Test Scenario                                   | Test Steps                                                                 | Test Data                     | Expected Result                                                       | Priority |
|-------|--------------------------------------------------|----------------------------------------------------------------------------|-------------------------------|------------------------------------------------------------------------|----------|
| TC001 | Upload a valid file                              | Click upload, choose a valid file, and submit                             | file.pdf (2MB)                | File should upload successfully                                       | High     |
| TC002 | Upload a file with unsupported format            | Try uploading .exe or .bat file                                           | virus.exe                     | Error message: "Unsupported file format"                              | High     |
| TC003 | Upload a file exceeding size limit               | Try uploading a file > 5MB (if 5MB is the limit)                          | file.zip (10MB)               | Error: "File size exceeds limit"                                      | High     |
| TC004 | Upload multiple files at once                    | Select 2-3 files simultaneously                                           | img1.jpg, img2.png            | All files should upload or error for unsupported ones                 | Medium   |
| TC005 | Cancel upload in-progress                        | Start uploading and cancel halfway                                        | file.mov (large)              | Upload should be aborted, no file saved                               | Medium   |
| TC006 | Download valid file                              | Click on file download link                                               | sample.pdf                    | File should download successfully                                     | High     |
| TC007 | Download with broken link                        | Click a download link pointing to a non-existent file                     | missing.docx                  | Error or 404 message should appear                                    | High     |
| TC008 | Upload with special characters in filename       | Upload file with name: `my#file@2024.pdf`                                 | my#file@2024.pdf              | File should upload with correct name preserved                        | Medium   |
| TC009 | Upload an empty file                             | Upload a 0-byte file                                                      | empty.txt                     | System should accept/reject based on requirements                     | Low      |
| TC010 | Download file with spaces in filename            | Download file named "my file.pdf"                                         | my file.pdf                   | Should download properly with name preserved                          | Medium   |
| TC011 | Upload with long filename                        | Upload file with very long name                                           | 256_chars_name.docx           | Should handle long names gracefully                                   | Medium   |
| TC012 | Upload file with duplicate name                  | Upload same file name twice                                               | test.docx (twice)             | Either overwrite, rename, or show warning based on logic              | High     |
| TC013 | Upload when offline or server is down            | Disconnect network and try to upload                                      | anyfile.jpg                   | Upload should fail with appropriate error                             | High     |
| TC014 | Download in unsupported browser                  | Use old browser (IE11)                                                    | sample.pdf                    | File should still download or fallback message shown                  | Medium   |
| TC015 | Upload via drag and drop                         | Drag file into dropzone (if supported)                                    | resume.pdf                    | File should be accepted and uploaded                                  | Medium   |
| TC016 | File preview before upload                       | Upload image or document and preview enabled                              | img.png                       | Should show preview before final submit                               | Low      |
| TC017 | Upload multiple file types together              | Select PDF, PNG, and XLSX at once                                         | mixed files                   | Only allowed types should upload                                      | Medium   |
| TC018 | Upload with slow internet                        | Simulate throttled connection                                             | large file                    | Upload should complete or timeout with error                          | Medium   |
| TC019 | Download and open file after upload              | Upload then download and open file                                        | report.pdf                    | File content should be intact                                         | High     |
| TC020 | Upload same file name, different content         | Upload test1.pdf (v1), then test1.pdf (v2)                                | Same name, different data     | System should detect duplicate or version                             | Medium   |
| TC021 | Upload password-protected file                   | Try uploading a password-locked file                                      | secure.docx                   | Should be accepted or rejected based on config                        | Low      |
| TC022 | Upload file during form submission               | Upload as part of multi-field form                                        | profile.jpg                   | File should be retained on submit                                     | High     |
| TC023 | Validate upload progress bar                     | Upload large file and observe progress                                    | movie.mp4                     | Progress bar should reflect upload status                             | Low      |
| TC024 | Resume paused upload (if supported)              | Pause upload then resume                                                  | 50MB zip                      | Should resume from where left off                                     | Low      |
| TC025 | Download without login                           | Attempt to download file while logged out                                 | public_file.pdf               | Should either allow or redirect to login                              | High     |
| TC026 | Upload file to incorrect field                   | Upload image in a "Resume Upload" field                                   | image.png                     | Should give invalid file type/field error                             | Medium   |
| TC027 | File scan after upload                           | Upload file and trigger antivirus scan                                    | suspicious_file.exe           | Should quarantine or block file                                       | Medium   |
| TC028 | File name sanitization                           | Upload file with script tag in name: `<script>.jpg`                      | <script>.jpg                 | Name should be sanitized to prevent XSS                               | High     |
| TC029 | Upload same file in different formats            | Upload `report.pdf` and `report.docx`                                     | Two formats                   | Both should upload as separate entries                                | Low      |
| TC030 | Download from different devices                  | Login on mobile and try to download file                                  | mobile browser                | File should download correctly on mobile                              | Medium   |

---

---

## Conclusion

The above test cases provide a thorough approach to validating the file upload and download functionalities in a web application. These tests ensure that users can seamlessly upload and download files, while also handling edge cases such as unsupported file types, oversized files, and network interruptions. By covering various scenarios, including security checks, device compatibility, and error handling, these tests contribute to a smooth, reliable user experience.

It’s essential to test across multiple browsers and devices to ensure that the file handling mechanisms are robust and consistent. Additionally, any security vulnerabilities, such as malicious file uploads, should be actively mitigated.

By executing these tests, QA teams can ensure that the file management features meet the highest standards for usability, security, and performance.

---

**Prepared by:** [Pratik Joshi]   
**Module:** File Upload & Download Testing
