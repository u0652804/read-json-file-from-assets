# read-json-file-from-assets

1. read file from assets as String type

    loadJSONFromAsset("test.json");

    public String loadJSONFromAsset(String jsonFileName) {
        try {
            InputStream inputStream = getAssets().open("jsonFileName");
            int size = inputStream.available();
            byte[] buffer = new byte[size];
            inputStream.read(buffer);
            inputStream.close();
            String str = new String(buffer, "UTF-8");
            return str;
        } catch (IOException ex) {
            ex.printStackTrace();
        } 
        return null;
    }
    
2. convert to JSONObject

    JSONObject jobj = new JSONObject(loadJSONFromAsset("test.json"));
    // use jobj like below
    jobj.getInt("a");
    jobj.getString("b");
    jobj.put("c", "cccc");
