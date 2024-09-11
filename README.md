# fintech-chatbot

To run the Python program for speech-to-text, first install the following:

```bash
sudo apt install ffmpeg
sudo apt install libespeak1
sudo apt install portaudio19-dev
sudo apt install python3-tk
sudo apt install python3-pil python3-pil.imagetk
```

Next, install the packages in the `requirements.txt` file, as follows:

```bash
pip install -r requirements.txt
```

Next, provide an OpenAI API Key, as follows:

```bash
export OPENAI_API_KEY="<OpenAI API Key>"
```

In the Python program file, fill-in the details. These can be obtained from the SingleStore portal.

```bash
s2_user = "<username>"
s2_password = "<password>"
s2_host = "<host>"
s2_port = <port>
s2_db = "<database>"
db = SQLDatabase.from_uri(
        f"mysql+pymysql://{s2_user}:{s2_password}@{s2_host}:{s2_port}/{s2_db}"
        "?ssl_ca=/path/to/singlestore_bundle.pem"
)
```

The `singlestore_bundle.pem` file is required if using the **Free Shared Tier**, otherwise this line can be removed:

```bash
"?ssl_ca=/path/to/singlestore_bundle.pem"
```

Finally, run the Python program, as follows:

```bash
python3 record-transcribe-visualise-speak-full.py
```