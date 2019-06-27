# jquery-magicsearch-plus

an input plugin based on jquery
 

## Changes Log

### v1.0.4.1 2019-06-27

1. Feature: Able to set criteria to enable dynamic filtering through Ajax , tested on singile and multiple autocomplete

Using with Asp.net Mvc :

 $('#CountryId').magicsearch({
            id: 'Value', 
            format: '%Name% · %Value%',
            fields: ['Name', 'Value'],
            noResult: 'no result found',
            dataSource: "@Url.Action("SearchCountris", "Utility", new { Area = "Common" })",
            AjaxUrl: "@Url.Action("SearchCountris", "Utility", new { Area = "Common" })",
            type: 'ajax',
            ajaxOptions: {
                success: function(data) {
                    alert('This is dynamic filtering!');
                }
            },
        });
 
  <div class="form-group">
        @Html.LabelFor(model => model.CountryId, htmlAttributes: new { @class = "control-label col-md-2" })
        <div class="col-md-10">
            @Html.EditorFor(model => model.CountryId, new { htmlAttributes = new { @class = "form-control", id = "CountryId" , type = "text" , autocomplete = "off", data_id = ViewBag.CountryId } })
            @Html.ValidationMessageFor(model => model.CountryId, "", new { @class = "text-danger" })
        </div>
    </div>
