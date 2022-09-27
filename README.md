# FirebaseSignUpSignEmail
#@Step -1 -> add firebase auth dependency
    implementation 'com.google.firebase:firebase-auth:21.0.8'
 
 #@step-2 -> connecting to firebase and enabling email and password authentication into firebase .
 
 #@step-3 -> on registration page (registering user with email $ password
 
 FirebaseAuth auth= FirebaseAuth.getInstance();
 auth.createUserWithEmailAndPassword(email, password)
                            .addOnCompleteListener(MainActivity.this, new OnCompleteListener<AuthResult>() {
@Override
public void onComplete(@NonNull Task<AuthResult> task) {
if (task.isSuccessful()) {
  Log.d(TAG, "onComplete:  Successfully Logged in. ");
Toast.makeText(MainActivity.this, " Registered Successfully", Toast.LENGTH_SHORT).show();
} else {
Toast.makeText(MainActivity.this, "Failed to be as  Registered" + task.getResult(), Toast.LENGTH_SHORT).show();
}
}
});

#@step -4 -> on login page ( login firebase with email and password ) 
FirebaseAuth firebaseAuth= FirebaseAuth.getInstance();

firebaseAuth.signInWithEmailAndPassword(loginBinding.etLoginEmail.getText().toString(), loginBinding.etPwd.getText().toString())
                        .addOnCompleteListener(new OnCompleteListener<AuthResult>() {
@Override
public void onComplete(@NonNull Task<AuthResult> task) {
if (task.isSuccessful()) {                                    
loginBinding.etLoginEmail.getText().toString());
loginBinding.etLoginEmail.getText().toString());
} else {                                                                        Toast.makeText(getApplicationContext(), " Invalid email/password", Toast.LENGTH_SHORT).show();
}
}
});
