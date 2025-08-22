# HypixelStatusChecker
import java.net.http.HttpClient;
import java.net.http.HttpRequest;
import java.net.http.HttpResponse;
import java.net.URI;

public class HypixelAPITest {
    public static void main(String[] args) throws Exception {

        String apiKey = "your hypixel API";
        String uuid = "friends uuıd";

        // Hypixel status endpoint
        String url = "https://api.hypixel.net/status?key=" + apiKey + "&uuid=" + uuid;

        // HTTP client oluştur
        HttpClient client = HttpClient.newHttpClient();

        // GET isteği hazırla
        HttpRequest request = HttpRequest.newBuilder()
                .uri(URI.create(url))
                .build();

        // İstek gönder ve cevabı string olarak al
        HttpResponse<String> response = client.send(request, HttpResponse.BodyHandlers.ofString());

        // JSON cevabını ekrana yazdır
        System.out.println(response.body());
    }
}
