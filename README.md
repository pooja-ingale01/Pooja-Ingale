<html>
<head>
    <title> Simple HTML Page </title>
</head>
    <table>
        <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Mobile</th>
            <th>Email</th>
        </tr>
        <tr>
            <td>1</td>
            <td>xyz</td>
            <td>9999999999</td>
            <td>abc@gmail.com</td>
        </tr>
        <tr>
            <td>2</td>
            <td>abc</td>
            <td>9555999999</td>
            <td>xyz@gmail.com</td>
        </tr>
    </table>


    <!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>jQuery Add / Remove Table Rows</title>
<style>
    table{
        width: 100%;
        margin: 20px 0;
        border-collapse: collapse;
    }
    table, th, td{
        border: 1px solid #cdcdcd;
    }
    table th, table td{
        padding: 5px;
        text-align: left;
    }
</style>
<script src="https://code.jquery.com/jquery-3.5.1.min.js"></script>
<script>
    $(document).ready(function(){
        $(".add-row").click(function(){
            var id = $("#id").val();
            var name = $("#name").val();
            var mobile = $("#mobile").val();
            var email = $("#email").val();
            var markup = "<tr><td><input type='checkbox' name='record'></td><td>" + name + "</td><td>" + mobile + "</td><td>" + email + "</td></tr>";
            $("table tbody").append(markup);
        });
        
        // Find and remove selected table rows
        $(".delete-row").click(function(){
            $("table tbody").find('input[name="record"]').each(function(){
                if($(this).is(":checked")){
                    $(this).parents("tr").remove();
                }
            });
        });
    });    
</script>
</head>
<body>
    <form>
        <input type="number" id="id" placeholder="ID">
        <input type="text" id="name" placeholder="Name">
        <input type="text" id="mobile" placeholder="Mobile">
        <input type="text" id="email" placeholder="Email Address">
        <input type="button" class="add-row" value="Add Row">
    </form>
    <table>
        <thead>
            <tr>
                <th>Select</th>
                <th>Name</th>
                <th>Mobile</th>
                <th>Email</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td><input type="checkbox" name="record"></td>
                <td>xyz</td>
                <td>9999999999</td>
                <td>abc@mail.com</td>
            </tr>
        </tbody>
    </table>
    <button type="button" class="delete-row">Delete Row</button>
</body> 


