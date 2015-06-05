# video_players
Holds various code blocks for playing video files
function playTutVideoClickOnVocab (){
	

	if (playClickOnVocabTutsFirstTime == 0) {

	
	vid_input = 'quiz_func_clickonvocab';

	//var videoFileMp4 = $('#VideoTut').attr('src', 'media/tuts/' + vid_input + '.mp4');
	//var videoFileWebm = $('#VideoTut').attr('src', 'media/tuts/' + vid_input + '.webm');
		
	//var newTutorialDiv = '<div id=\"Quiz_VidTut_Holder\" width=\"242\" height=\"162\" class=\"\"></div> <!-- end of Quiz_VidTut_Holder --!>';
	var newTutorialTag = '<video id=\"VideoTut\" width=\"242\" height=\"162\" autoplay>Your browser does not support the video tag.</video>';
	//$('#Quiz_Content_Holder').append(newTutorialDiv);
	$('#Quiz_VidTut_Holder').append(newTutorialTag);
	
	var videoFile1Add = $('#VideoTut').attr('src', 'media/tuts/' + vid_input + '.mp4');

	$('#Quiz_VidTut_Holder').fadeIn(300);
	$('#VideoTut').fadeIn(300);
		
	var initVidDuration = document.getElementById("VideoTut");
			initVidDuration.onloadedmetadata = function (){
			lenVideo = initVidDuration.duration;

					$("#VideoTut").bind("ended", function(){
					var vid_ended = document.getElementById("VideoTut").ended;

							if (vid_ended = true) {
							$("#VideoTut").unbind();
							playClickOnVocabTutsFirstTime = 1;
							$('#Quiz_VidTut_Holder').fadeOut(300);
							$('#Quiz_Buttons_Holder').fadeIn(200);
							$('.vocab_button').hide();
							$('#quiz_button_next').hide();
							$('.listening_button').hide();
							$('#quiz_button_yes').fadeIn(200);
							$('#quiz_button_no').fadeIn(200);
							$('.quizword_inactive').addClass( 'quizword' ).removeClass('quizword_inactive');
			
								// show got it or not > then fade in next button				
							}  // end of if
			
					});	// end of .bind
				} // end of onloadedmetadata
	} // end of if
	else {
			$('#Quiz_VidTut_Holder').hide();
			$('.quizword_inactive').addClass( 'quizword' ).removeClass('quizword_inactive');
			$('#Quiz_Buttons_Holder').fadeIn(200);
			$('.vocab_button').hide();
			$('#quiz_button_next').hide();
			$('.listening_button').hide();
			$('#quiz_button_yes').fadeIn(200);
			$('#quiz_button_no').fadeIn(200);

		}	
}
