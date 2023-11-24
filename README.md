<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>S3 Image Viewer</title>
</head>
<body>
    <h1>S3 이미지 출력 by 정환</h1>
    <form>
        <label for="fileName">파일명 (확장자 포함):</label>
        <input type="text" id="fileName" name="fileName">
        <button type="button" onclick="loadImage()">출력</button>
    </form>
    <div id="imageContainer"></div>

    <script>
        function loadImage() {
            var fileName = document.getElementById("fileName").value;
            var container = document.getElementById("imageContainer");
            var image = document.createElement("img");

            // 입력한 파일명을 사용하여 S3 이미지 URL 생성
            //var s3ImageUrl = "https://my-userdata-sbj.s3.ap-northeast-2.amazonaws.com/" + encodeURIComponent(fileName);
            var s3ImageUrl = "https://my-test-shin1.s3.ap-northeast-2.amazonaws.com/" + encodeURIComponent(fileName);
           
            image.src = s3ImageUrl;
            container.innerHTML = '';  // 이미지를 출력하기 전에 이전 내용을 지웁니다.
            container.appendChild(image);
        }
    </script>
</body>
</html>
