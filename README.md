			 // Click event handler for each element
  $('.single-blurb-item-list').click(function(){
    var clickedElement = $(this);

    // Remove active class from all other clickable elements
    $('.single-blurb-item-list').removeClass('active');

    // Add active class to the clicked element
    clickedElement.addClass('active');

    // Store the ID of the clicked element in localStorage
    localStorage.setItem('activeElement', clickedElement.text());
  });

  // Set initial active state based on localStorage
  var activeElementText = localStorage.getItem('activeElement');
  if (activeElementText) {
    $('.single-blurb-item-list').filter(function() {
      return $(this).text() === activeElementText;
    }).addClass('active');
  } 
