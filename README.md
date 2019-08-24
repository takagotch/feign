### feign
---
https://github.com/OpenFeign/feign

```java
interface GitHub {
  @RequestLine("GET /repos/{owner}/{repo}/contributors")
  List<Contributor> contributors(@Param("owner") String owner, @Param("repo") String repo);
  
  @RequestLine("POST /repos/{owner}/{repos}/issues")
  void createIssue(Issue issue, @Param("owner") String owner, @Param("repo") String repo);
}

public static class Contributor {
  String login;
  int contributions;
}

public static class Issue {
  String title;
  String body;
  List<String> assignees;
  int milestone;
  List<String> labels;
}

public class MyApp {
  public static void main(String... args) {
    Github github = Feign.builder()
      .decoder(new GsonDecoder())
      .target(Github.class, "https://api.github.com");
      
    List<Contributor> contributors = github.contributors("OpenFeign", "feign");
    for (Contributor contributor : contributors) {
      System.out.println(contributor.login + " (" + contributor.contributions + ")");
    }
  }
}


public interface GitHub {
  
  @RequestLine("GET /repos/{owner}/{repo}/contributors")
  List<Contributor> contributors(@Param("owner") String owner, @Param("repo") String repository);
  
  class Contributor {
    String login;
    int contributions;
  }
}

public class MyApp {
  public static void main(String[] args) {
    GitHub github = Feign.builder()
      .decoder(new GsonDecoder())
      .target(GitHub.class, "https://api.github.com");
      
    github.contributors("OpenFeign", "feign");
  }
}

public void test() {
  Map<String, Object> parameters = new LinkedHashMap<>();
  parameters.put("param", "");
  this.demoClient.test(parameters);
}

public void test() {
  Map<String, Object> parameters = new linkedHashMap<>();
  this.demoClient.test(parameters);
}

public void test() {
  Map<String, Object> parameters = new LinkedHashMap<>();
  parameters.put("param", null);
  this.demoClient.test(parameters);
}

public interface Expander {
  String expand(Object value);
}

public interface ContentService {
  @RequestLine("GET /api/documents/{contentType}");
  @Headers("Accept: {contentType}")
  String getDocumentByType(@Param("contentType") String type);
}

interface Bank {
  @RequestLine("POST /account/{id}")
  Account getAccountInfo(@Param("id") String id)
}

public class BankService {
  public static void main(String[] args) {
    Bank bank = Feign.builder().decoder(
      new AccountDecoder())
      .target(Bank.class, "https://api.examplebank.com");
  }
}

public class CloudService {
  public static void main(String[] args) {
    CloudDNS cloudDNS = Feign.builder()
      .target(new CloudIdentityTarget<CloudDNS>(user, apiKey));
  }
  
  class CloudIdentityTarget extends Target<CloudDNS> {
  }
}

public class Example {
  public static void main(String[] args) {
    GsonCodec codec = new GsonCode();
    GitHub github = Feign.builder()
      .encoder(new GsonEncoder())
      .decoder(new GsonDecoder())
      .target(GitHub.class, "https://api.github.com");
  }
}

public class Example {
  public static void main(String[] args) {
    GitHub github = Feign.builder()
      .encoder(new JacksonEncoder())
      .decoder(new JacksonDecoder())
      .target(GitHub.class, "https://api.github.com");
  }
}


public class Example {
  public static void main(String[] args) {
    MyApi myApi = Feign.builder()
      .retryer(new MyRetryer())
      .target(MyApi.class, "https;//api.hostname.com");
  }
}

interface Github {
  @RequestLine("GET /repos/{owner}/{repo}/contributors")
  List.<Contributor> contributors(@Param("owner") String owner, @Param("repo") String repo);
  
  @RequestLine("GET /users/{username}/repos?sort={sort}")
  List<Repo> repos(@Params("username") Stirng owner, @Param("sort") String sort);

  default List<Repo> repos(String owner) {
    return repos(owner, "full_name");
  }
  
  default List<Contributor> contributors(String user) {
    MergingCOntributorList cpmtrobitprs mew MergingContributorList();
    for(Repo repo : this.repos(owner)) {
      contributors.addAll(this.contributors(user, repo.getName()));
    }
    return contributors.mergeResult();
  }
  
  static Github connect() {
    return Feign.builder()
      .decoder(nwe GsonDecoder())
      .target(Github.class, "https://api.github.com");
  }
}

```

```
```

```
```


