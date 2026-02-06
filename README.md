# Somnio Cursor Rules

🧠 A curated collection of [Cursor](https://cursor.com/) development rules used internally at **Somnio Software**.

## ✨ Purpose

This repository helps standardize AI-assisted development across our team. By defining clear, consistent rules, Cursor can better understand our project's conventions and generate higher-quality code that aligns with our standards.

Whether you're working with Flutter or NestJS, these rules are here to make your dev experience smoother, faster, and more consistent.

## 📁 Structure

- `.cursor/rules/`: General rules that apply to all projects regardless of framework or technology.
- `.cursor/rules/flutter/`: Cursor rules tailored for Flutter and Dart projects.
- `.cursor/rules/nestjs/`: Cursor rules tailored for NestJS backends.

---

## 🚀 NestJS Rules

Comprehensive rules for building robust NestJS backends with TypeScript.

### Available Rules

| Rule File | Glob Pattern | Purpose |
|-----------|--------------|---------|
| `nestjs-dto-validation.mdc` | `**/*.dto.ts` | DTO structure, class-validator, class-transformer, Swagger decorators |
| `nestjs-service-patterns.mdc` | `**/*.service.ts` | Service layer patterns: transactions, validation, error handling |
| `nestjs-controller-patterns.mdc` | `**/*.controller.ts` | Controller patterns: decorators, response formatting, guards |
| `nestjs-repository-patterns.mdc` | `**/*.repository.ts` | Repository pattern: parameterized methods, select objects, soft deletes |
| `nestjs-testing-unit.mdc` | `**/*.spec.ts` | Unit test patterns: mocking, structure, assertions |
| `nestjs-testing-integration.mdc` | `**/*.integration.spec.ts` | Integration test patterns: database, cleanup, isolation |
| `nestjs-error-handling.mdc` | `**/*exception*.ts`, `**/*error*.ts`, `**/*filter*.ts` | Exception filters, validation errors, error enums/maps |
| `nestjs-module-structure.mdc` | `**/*.module.ts` | Module organization: imports, exports, providers, feature structure |
| `nestjs-typescript.mdc` | `src/modules/**/*.ts` | TypeScript guidelines, naming conventions, NestJS principles |

### Usage

Reference rules in Cursor using the `@` syntax:

```
@nestjs-dto-validation
@nestjs-service-patterns
@nestjs-controller-patterns
```

Rules are automatically applied based on glob patterns when editing matching files.

### Key Patterns Covered

**DTO Validation**
- class-validator decorators (`@IsNotEmpty`, `@IsEmail`, `@ValidateNested`)
- class-transformer patterns (`@Type`, `@Expose`, `@Exclude`, `@Transform`)
- Swagger documentation (`@ApiProperty`, `@ApiPropertyOptional`)
- Separate DTOs for create, update, query, response operations

**Service Layer**
- Object parameters with destructuring (RO-RO pattern)
- Transaction management with `prisma.$transaction()`
- Validation before operations
- Service composition via constructor injection

**Repository Pattern**
- Abstract repository interfaces
- Parameterized methods: `findAll({ skip, take, where, orderBy, select })`
- Reusable select objects with `satisfies Prisma.XxxSelect`
- Soft delete pattern (`deletedAt: null` filter)
- Return `{ data, count }` for list operations

**Controller Patterns**
- Guard decorators (`@UseGuards()`)
- Swagger documentation (`@ApiTags`, `@ApiOperation`, `@ApiResponse`)
- Response formatting
- File upload handling

**Testing**
- Unit tests with mocked dependencies
- Integration tests with real database
- Test data builders
- Arrange-Act-Assert pattern

**Error Handling**
- Validation error enums
- Error message maps
- Custom exception filters
- Consistent error response structure

---

## 🦋 Flutter Rules

Comprehensive rules for building Flutter applications with Dart.

### Available Rules

| Rule File | Glob Pattern | Purpose |
|-----------|--------------|---------|
| `flutter-architecture.mdc` | `**/*.dart` | Layered architecture: Data, Repository, Business Logic, Presentation |
| `flutter-ai-rules.mdc` | `**/*.dart` | General Flutter best practices, SOLID principles, state management |
| `bloc-test.mdc` | `**/*bloc_test.dart` | BLoC testing patterns and conventions |
| `flutter-testing.mdc` | `**/*_test.dart` | Flutter testing best practices |
| `dart-model-from-json.mdc` | `**/*.dart` | JSON model generation patterns |

### Key Patterns Covered

**Layered Architecture**
- Data Layer (API clients, storage)
- Repository Layer (data composition)
- Business Logic Layer (BLoC/Cubit)
- Presentation Layer (Widgets)

**Testing**
- BLoC test structure and patterns
- Widget testing best practices
- Mocking with mocktail

---

## 📚 Recommended Reads & Open Source Community Rules

- Official Cursor rules documentation:
  [https://docs.cursor.com/context/rules](https://docs.cursor.com/context/rules)

- AI Prompts Library: [https://www.jointakeoff.com/prompts](https://www.jointakeoff.com/prompts)

## 🤝 Contributing

Found or created a rule that's working wonders in your project? We'd love to add it to this collection!

- Open a pull request with a short explanation of the rule.
- Make sure it's well-tested and specific to Flutter or NestJS development.
- Include Good/Bad code examples for clarity.

## 💡 Why Use Rules?

Cursor rules give the AI context that goes beyond a single file or prompt. With well-written rules, we ensure:

- Consistency across all our repositories.
- AI outputs that follow our naming, architecture, and design standards.
- A smoother onboarding experience for new developers using AI tooling.

---

Together, let's build a smarter, faster, more aligned development workflow. 💜
