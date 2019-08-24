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













```

```
```

```
```


