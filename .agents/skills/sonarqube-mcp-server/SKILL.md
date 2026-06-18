```markdown
# sonarqube-mcp-server Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill covers the core development patterns and workflows used in the `sonarqube-mcp-server` Java codebase. It documents coding conventions, commit practices, and standard procedures for updating dependencies and implementing features, ensuring consistency and maintainability across contributions.

## Coding Conventions

### File Naming
- **Java files** use **PascalCase**.
  - Example: `MyService.java`, `UserRepository.java`

### Import Style
- **Relative imports** are preferred.
  - Example:
    ```java
    import com.mycompany.project.module.MyClass;
    ```

### Export Style
- **Named exports** are used for Java classes.
  - Example:
    ```java
    public class MyService {
        // ...
    }
    ```

### Commit Patterns
- Commits reference tickets/issues.
- Prefixes are used (e.g., `SONAR-1234:`).
- Commit messages average around 65 characters.
  - Example:
    ```
    SONAR-5678: Update SonarLint Core to version 9.2.1
    ```

## Workflows

### Update Dependencies
**Trigger:** When you need to update an external dependency or tool version (e.g., SonarLint Core, CI GitHub Actions).  
**Command:** `/update-dependency`

1. Identify the dependency or tool to update.
2. Update its version in all relevant configuration files:
    - `gradle.lockfile`
    - `gradle/libs.versions.toml`
    - `its/build.gradle.kts`
    - `its/gradle.lockfile`
    - `.github/workflows/*.yml`
3. Commit your changes with a message referencing the dependency and new version.
    - Example commit message:
      ```
      SONAR-1234: Bump SonarLint Core to 9.3.0
      ```
4. Open a pull request for review.

#### Example: Updating a Dependency in `gradle/libs.versions.toml`
```toml
[versions]
sonarlint-core = "9.3.0"
```

### Feature or Behavior Change with Tests
**Trigger:** When you want to add a new feature or modify existing behavior, ensuring it is tested.  
**Command:** `/feature-change`

1. Modify or add implementation files in `src/main/java/**`.
2. Update or add corresponding test files in `src/test/java/**` or `its/src/test/java/**`.
3. Update configuration or resource files if needed (e.g., `Dockerfile`, files in `src/main/resources/**`).
4. Commit all related changes together.
    - Example commit message:
      ```
      SONAR-2345: Add support for custom rule configuration
      ```
5. Open a pull request for review.

#### Example: Adding a New Feature and Test
```java
// src/main/java/com/mycompany/project/FeatureService.java
public class FeatureService {
    public boolean isEnabled() {
        return true;
    }
}
```
```java
// src/test/java/com/mycompany/project/FeatureServiceTest.java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class FeatureServiceTest {
    @Test
    void testIsEnabled() {
        FeatureService service = new FeatureService();
        assertTrue(service.isEnabled());
    }
}
```

## Testing Patterns

- **Testing framework:** Not explicitly detected; likely JUnit for Java.
- **Test files:** Placed alongside source files in `src/test/java/**` or `its/src/test/java/**`.
- **Naming:** Test classes typically mirror the class under test, suffixed with `Test`.
  - Example: `FeatureService.java` → `FeatureServiceTest.java`
- **Test method example:**
    ```java
    @Test
    void testSomething() {
        // assertions here
    }
    ```
- **Note:** Some `.test.ts` patterns are present, but primary language is Java.

## Commands

| Command             | Purpose                                               |
|---------------------|-------------------------------------------------------|
| /update-dependency  | Update external dependencies or tool versions         |
| /feature-change     | Implement a feature or modify behavior with tests     |
```
