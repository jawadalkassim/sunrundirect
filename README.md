# sunrundirect
if (res.code == 200) {
                                                            const posted = res?.body?.posted || false;
                                                            if (posted) {
                                                                pollForSuccess(res.body.conversion_id, success);
                                                            } else {
                                                                measureSubmissionDuration.capture('complete');
                                                                success();
                                                            }
                                                        } else {

                                                            $("#loader").hide();
                                                            $('#form_box').show();
                                                            const question = res?.body?.question || 10;
                                                            const fieldName = getFieldName(question);
                                                            $('.btn-next').removeAttr('disabled');
                                                            progressFieldsetSteps(question, fieldName);
                                                            $("input, select").removeAttr('disabled', 'disabled');
                                                        }
                                                    
