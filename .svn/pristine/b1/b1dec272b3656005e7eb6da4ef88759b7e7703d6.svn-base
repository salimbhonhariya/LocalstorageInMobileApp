

function getprayerWithZipCode() {

    var zipcode = $('#prayer-location-input').val();
    
        var location = $('#prayer-location-input').val();
        var today = new Date();
        var dd = today.getDate();
        var mm = today.getMonth() + 1; //January is 0!
        var yyyy = today.getFullYear();

        if (dd < 10) {
            dd = '0' + dd
        }

        if (mm < 10) {
            mm = '0' + mm
        }
        today = mm + '-' + dd + '-' + yyyy;
       // document.write(today);
        var toDaydate = today;

    var queryString =
        'http://muslimsalat.com/' + location + '/' + toDaydate + '.json?key=7fa488b615f24fb2ee4f8be1b3292b9e';
   // var queryString = 'http://muslimsalat.com/canton,mi,usa/05-11-2016.json?key=7fa488b615f24fb2ee4f8be1b3292b9e';

    $.getJSON(queryString, function (results) {

        showprayerData(results);

    }).fail(function (jqXHR) {
        $('#error-msg').show();
        $('#error-msg').text("Error retrieving data. " + jqXHR.statusText);
    });
    //Keep the screen to the same page
    return false;
}

function showprayerData(results) {

    if (results.status_valid ===1) {

        $('#error-msg').hide();
        $('#prayer-data').show();
        $('#date').text(new Date());
        $('#title').text(results.title);
        $('#TimeCalculationMethod').text(results.prayer_method_name);
        $('#fajr').text(results.items[0].fajr);
        $('#Zuhar').text(results.items[0].dhuhr);
        $('#Asar').text(results.items[0].asr);
        $('#Maghrib').text(results.items[0].maghrib);
        $('#isha').text(results.items[0].isha);

    }
    else {
        $('#prayer-data').hide();
        $('#error-msg').show();
        $('#error-msg').text("Error retrieving data. ");
    }

}


function Credentials() {
    //debugger;
    var uname = $("[name='username']").val();
    var _email = $("[name='email']").val();
    alert("Inserting into local storage");
    alert(uname);
    alert(_email);

    window.localStorage.setItem("username", uname);
    window.localStorage["email"] = _email;

    $.mobile.changePage("#page2", { reverse: false, transition: "slide" });


    $('#output').html("Username: " + window.localStorage.getItem("username") + "<br>" +
                        "Email: " + window.localStorage["email"]
                    );
    alert("Reading from local storage");
    alert(window.localStorage.getItem("username"));
    alert(window.localStorage.getItem("email"));

   // $('#page2').show();
    return false;
}
