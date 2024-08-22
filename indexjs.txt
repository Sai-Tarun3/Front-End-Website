let studentImgEle = document.getElementById("student-img");

// List of images
let imgsLst = [
    "https://w7.pngwing.com/pngs/453/64/png-transparent-cisco-systems-computer-network-organization-logo-nasdaq-csco-others-computer-network-text-trademark-thumbnail.png",
    "https://directlinedev.com/media/page_photos/0002/photo_2431.normal.png",
    "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTXj3F-sF9xgF3uP5H1zK6cTqhrj8Nr46eSqg&s",
    "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQiTlMahNL6EAk2jOm-uukqiZKvYGB_dUOKqA&s",
    "https://e7.pngegg.com/pngimages/604/618/png-clipart-larsen-toubro-limited-mmh-architectural-engineering-business-l-t-hydrocarbon-engineering-business-blue-text-thumbnail.png",
    "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSY_XcOiHQTtKmJYTAe6ytb9sSAprKDTf62VQ&s",
    "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRyA0GgQHJIRtyq5TCColOyUU8mo7dZsSAs5A&s",
    "https://cdn.prod.website-files.com/638aec50b9a23cec17b8c4d1/6523e4de85bfabb52fcf4dfd_Tata_Consultancy_Services_Logo.svg.png",
    "https://w7.pngwing.com/pngs/898/916/png-transparent-oracle-corporation-logo-computer-software-business-company-logo-miscellaneous-angle-company-thumbnail.png",
    "https://cdn.prod.website-files.com/638aec50b9a23cec17b8c4d1/63e36358b9ea27326ff510d5_Logo-True-Colors-original.png",
    "https://cdn.prod.website-files.com/638aec50b9a23cec17b8c4d1/642d44e8d4d7fb27af4674e7_Infosys_logo.svg.png",
    "https://360digit.b-cdn.net/assets/admin/ckfinder/userfiles/images/blog/blog/hyderabad1/Wipro-it-companies-in-hyderabad%20(1).png",
    "https://zolostays.com/blog/wp-content/uploads/2019/07/accenture.jpg",
    "https://zolostays.com/blog/wp-content/uploads/2019/07/deloitte.jpg",
    "https://zolostays.com/blog/wp-content/uploads/2019/09/download-6.png",
    "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT7L6HLCGP2bRnZOsL5L2D1uVlSOmFDAf4o2J-sJCbB_O2Q9eaHAnuPCzvZqO5NWCRHfBg&usqp=CAU",
    "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTKR_Eqtm1W7RWPdhG88WD1xiNUfTBNvf9vYQ&s",
    "https://1000logos.net/wp-content/uploads/2021/04/ADP-logo.png",
    "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTr3snlm4h7bWj7NAUX22vYC4zYzQ3WyMfDQQ&s"
];

let index = 0;

function addImage() {
    if (index >= imgsLst.length) {
        index = 0; // Reset index if it exceeds the list length
    }
    let imgEle = document.createElement("img");
    imgEle.src = imgsLst[index];
    imgEle.alt = "img";
    imgEle.height = 50;
    imgEle.width = 70;  
    
    studentImgEle.appendChild(imgEle);

    index++;
}

// Function to double the list of images
function addimgages() {
    imgsLst = [...imgsLst, ...imgsLst];
}

// Call addImage every 100 milliseconds
setInterval(addImage, 100);

// Double the list of images every 1000 milliseconds (1 second)
setInterval(addimgages, 1000);






        function searchTable() {
    const input = document.getElementById('search');
    const filter = input.value.toLowerCase();
    const table = document.getElementById('courseTable');
    const tr = table.getElementsByTagName('tr');

    for (let i = 1; i < tr.length; i++) {
        const td = tr[i].getElementsByTagName('td');
        let found = false;
        for (let j = 0; j < td.length; j++) {
            if (td[j]) {
                if (td[j].innerText.toLowerCase().indexOf(filter) > -1) {
                    found = true;
                    break;
                }
            }
        }
        tr[i].style.display = found ? '' : 'none';
    }
}

function updateEntries() {
    const select = document.getElementById('entries');
    const limit = parseInt(select.value);
    const table = document.getElementById('courseTable');
    const tr = table.getElementsByTagName('tr');

    for (let i = 1; i < tr.length; i++) {
        tr[i].style.display = i <= limit ? '' : 'none';
    }
}




// document.querySelector('.left-scroll-icon').addEventListener('click', function() {
//     document.querySelector('.job-roles-container').scrollBy({
//         left: -300, 
//         behavior: 'smooth'
//     });
// });

// document.querySelector('.right-scroll-icon').addEventListener('click', function() {
//     document.querySelector('.job-roles-container').scrollBy({
//         left: 300, 
//         behavior: 'smooth'
//     });
// });



const leftScrollIcon = document.querySelector('.left-scroll-icon');
const rightScrollIcon = document.querySelector('.right-scroll-icon');
const jobRolesContainer = document.querySelector('.job-roles-container');

leftScrollIcon.addEventListener('click', () => {
    jobRolesContainer.scrollBy({
        top: 0,
        left: -200,  // Adjust this value based on how much you want to scroll
        behavior: 'smooth'
    });
});

rightScrollIcon.addEventListener('click', () => {
    jobRolesContainer.scrollBy({
        top: 0,
        left: 200,  // Adjust this value based on how much you want to scroll
        behavior: 'smooth'
    });
});



 // Get the search input element and the table body
 const searchInput = document.getElementById('searchInput');
 const tableBody = document.getElementById('tableBody');

 // Add an event listener to the search input
 searchInput.addEventListener('input', function() {
     // Convert the input value to lowercase for case-insensitive search
     const filter = searchInput.value.toLowerCase();
     
     // Loop through all table rows
     const rows = tableBody.getElementsByTagName('tr');
     for (let i = 0; i < rows.length; i++) {
         const companyName = rows[i].getElementsByTagName('td')[1]; // Company Name column
         const role = rows[i].getElementsByTagName('td')[2]; // Role column
         
         if (companyName || role) {
             const companyNameText = companyName.textContent || companyName.innerText;
             const roleText = role.textContent || role.innerText;
             
             // Check if the search input matches the company name or role
             if (companyNameText.toLowerCase().indexOf(filter) > -1 || roleText.toLowerCase().indexOf(filter) > -1) {
                 rows[i].style.display = '';
             } else {
                 rows[i].style.display = 'none';
             }
         }
     }
 });

 const reviewsLeftScrollIcon = document.querySelector('.reviews-left-scroll-icon');
 const reviewsRightScrollIcon = document.querySelector('.reviews-right-scroll-icon');
 const reviewsContainer = document.querySelector('.reviews-container');
 
 reviewsLeftScrollIcon.addEventListener('click', () => {
     reviewsContainer.scrollBy({
         top: 0,
         left: -200,  // Adjust this value based on how much you want to scroll
         behavior: 'smooth'
     });
 });
 
 reviewsRightScrollIcon.addEventListener('click', () => {
     reviewsContainer.scrollBy({
         top: 0,
         left: 200,  // Adjust this value based on how much you want to scroll
         behavior: 'smooth'
     });
 });
 







