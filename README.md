# SSD_Assignment
For this Project, I am building an image classifier
For the MLmodel I am using a keras model that's already been prebuild. The one that I'm using is VGG16, it's a prebuild image recognition model

- load image, and preprocess it into the correct shape that the model want
  
    image = load_img(image_path, target_size=(224,224))
    
    image = img_to_array(image)
    
    image = image.reshape((1, image.shape[0], image.shape[1], image.shape[2]))
    
- making prediction

    image = preprocess_input(image)
    
    yhat = model.predict(image)
    
    label = decode_predictions(yhat)

    label = label[0][0]
    
- and then return my prediction and gave it to my template
    
    classification = '%s (%.2f%%)' % (label[1], label[2]*100)
    
    return render_template('index.html', prediction=classification)
