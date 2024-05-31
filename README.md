# lab6
 // Функція, що створює інтерфейс-шифрувальник
 private ICryptoTransform CreateEnc(SymmetricAlgorithm AlgType)
 {
     if (AlgType is DESCryptoServiceProvider || AlgType is RC2CryptoServiceProvider)
         return AlgType.CreateEncryptor(Key, IV);
     else if (AlgType is TripleDESCryptoServiceProvider)
         return AlgType.CreateEncryptor(TripleKey, TripleIV);
     else if (AlgType is RijndaelManaged)
         return AlgType.CreateEncryptor(aesKey, aesIV);

     return null;
 }
