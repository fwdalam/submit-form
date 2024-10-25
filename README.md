
# submit-form
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Product Submission Form</title>
    <link rel="stylesheet" href="submit.css">
</head>

<body>
    <div class="form-container">
        <form action="/submit-product" method="POST" enctype="multipart/form-data" id="product-form">
            <label for="product-name">Enter Product Name:</label>
            <input type="text" id="product-name" name="product-name" placeholder="Type product name..." required>

            <label for="categories">Related Categories:</label>
            <select id="categories" name="categories" required>
                <option value="">-- Select a category --</option>
                <option value="electronics">Electronics</option>
                <option value="mobile-phones">Mobile Phones</option>
                <option value="accessories">Accessories</option>
                <option value="fashion">Fashion</option>
                <option value="footwear">Footwear</option>
                <option value="home-appliances">Home Appliances</option>
                <option value="kitchen">Kitchen</option>
                <option value="large-appliances">Large Appliances</option>
                <option value="books">Books</option>
                <option value="education">Education</option>
                <option value="stationery">Stationery</option>
                <option value="health-beauty">Health & Beauty</option>
                <option value="cosmetics">Cosmetics</option>
                <option value="furniture">Furniture</option>
                <option value="living-room">Living Room</option>
                <option value="home-decor">Home Decor</option>
                <option value="audio-equipment">Audio Equipment</option>
                <option value="photography">Photography</option>
                <option value="sports-outdoors">Sports & Outdoors</option>
                <option value="fitness">Fitness</option>
                <option value="transportation">Transportation</option>
                <option value="home-entertainment">Home Entertainment</option>
                <option value="wearables">Wearables</option>
                <option value="household-items">Household Items</option>
                <option value="cleaning-supplies">Cleaning Supplies</option>
                <option value="cooking">Cooking</option>
                <option value="fragrances">Fragrances</option>
                <option value="personal-care">Personal Care</option>
                <option value="outerwear">Outerwear</option>
                <option value="winter-collection">Winter Collection</option>
                <option value="gaming">Gaming</option>
                <option value="office-supplies">Office Supplies</option>
                <option value="bedroom">Bedroom</option>
                <option value="pharmacy">Pharmacy</option>
                <option value="health-wellness">Health & Wellness</option>
                <option value="prescription-drugs">Prescription Drugs</option>
                <option value="medical-supplies">Medical Supplies</option>
                <option value="surgical-instruments">Surgical Instruments</option>
                <option value="healthcare">Healthcare</option>
                <option value="medical-equipment">Medical Equipment</option>
                <option value="diagnostics">Diagnostics</option>
                <option value="mobility-aids">Mobility Aids</option>
                <option value="personal-protective-equipment">Personal Protective Equipment</option>
                <option value="antibiotics">Antibiotics</option>
                <option value="pain-relief">Pain Relief</option>
                <option value="over-the-counter">Over-the-Counter</option>
                <option value="allergy">Allergy</option>
                <option value="cardiovascular">Cardiovascular</option>
                <option value="diabetes">Diabetes</option>
                <option value="cold-cough">Cold & Cough</option>
                <option value="gastrointestinal">Gastrointestinal</option>
                <option value="topical-treatments">Topical Treatments</option>
                <option value="antifungal">Antifungal</option>
            </select>

            <label for="product-unit">Unit of the product:</label>
            <select id="product-unit" name="product-unit" required>
                <option value="1">1</option>
                <option value="2">2</option>
                <option value="3">3</option>
                <option value="4">4</option>
                <option value="5">5</option>
                <option value="6">6</option>
                <option value="7">7</option>
                <option value="8">8</option>
            </select>

            <textarea id="product-description" placeholder="Description of the product:" name="product-description" rows="4" required></textarea><br><br>

            <label for="delivery-date">Delivery time of the product:</label>
            <input type="date" id="delivery-date" name="delivery-date" required><br><br>

            <input type="text" id="location" placeholder="Location of product to be delivered:" name="location" required><br><br>

            <label for="product-image">Upload picture of the product:</label>
            <input type="file" id="product-image" name="product-image" accept="image/*" required><br><br>

            <button type="submit" id="submit-button">Submit</button>
        </form>
    </div>

    <script>
        const productCategories = {
            "iphone": ["Electronics", "Mobile Phones", "Accessories"],
            "laptop": ["Electronics", "Computers & Laptops", "Accessories"],
            "shoes": ["Fashion", "Footwear", "Sports"],
            "fridge": ["Home Appliances", "Kitchen", "Large Appliances"],
            "book": ["Books", "Education", "Stationery"],
            "makeup": ["Health & Beauty", "Cosmetics", "Personal Care"],
            "sofa": ["Furniture", "Living Room", "Home Decor"],
            "medicine": ["Pharmacy", "Health & Wellness", "Prescription Drugs"],
            "syringe": ["Medical Supplies", "Surgical Instruments", "Healthcare"]
            // Add more categories here
        };

        const productNameInput = document.getElementById("product-name");
        const categoriesSelect = document.getElementById("categories");

        productNameInput.addEventListener("input", function () {
            const productName = productNameInput.value.toLowerCase();
            const allOptions = Array.from(categoriesSelect.options);

            // Hide all options first
            allOptions.forEach(option => option.style.display = "none");
            categoriesSelect.value = "";  // Reset selection

            // Show options that match the product name
            for (let key in productCategories) {
                if (productName.includes(key)) {
                    productCategories[key].forEach(category => {
                        const matchedOption = allOptions.find(opt => opt.value === category.toLowerCase());
                        if (matchedOption) matchedOption.style.display = "block";
                    });
                }
            }
        });
    </script>
</body>
</html>
