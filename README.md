![Pterodactyl GraalVM](https://user-images.githubusercontent.com/18230443/209179431-6adf6e6c-09fd-4501-b420-90c5b1dd09e1.jpg)
![build graalvm](https://github.com/RikoDEV/pterodactyl-graalvm/actions/workflows/docker-image.yml/badge.svg)
![license mit](https://img.shields.io/badge/license-MIT-green)

GraalVM is a high-performance runtime that provides significant improvements in application performance and efficiency which is ideal for microservices. https://www.graalvm.org/

___

## Docker Container Configuration

| Java | Standard                               	| JDK                                        	 | Enterprise                                	 |
|------|----------------------------------------	|----------------------------------------------|---------------------------------------------|
| 11   | `ghcr.io/rikodev/pterodactyl-graalvm:11` | ❌                                          	| `ghcr.io/rikodev/pterodactyl-graalvm:11-EE` |
| 17   | `ghcr.io/rikodev/pterodactyl-graalvm:17` | `ghcr.io/rikodev/pterodactyl-graalvm:17-JDK` | `ghcr.io/rikodev/pterodactyl-graalvm:17-EE` |
| 19   | `ghcr.io/rikodev/pterodactyl-graalvm:19` | ❌                                          	| ❌                                          |
| 20   | ❌                                       | `ghcr.io/rikodev/pterodactyl-graalvm:20-JDK` | ❌                                          |
| 21   | ❌                                     	 | `ghcr.io/rikodev/pterodactyl-graalvm:21-JDK`	| ❌                                          |
| 22   | ❌                                     	 | `ghcr.io/rikodev/pterodactyl-graalvm:22-JDK`	| ❌                                          |
| 23   | ❌                                     	 | `ghcr.io/rikodev/pterodactyl-graalvm:23-JDK`	| ❌                                          |
| 24   | ❌                                     	 | `ghcr.io/rikodev/pterodactyl-graalvm:24-JDK`	| ❌                                          |
| 25   | ❌                                     	 | `ghcr.io/rikodev/pterodactyl-graalvm:25-JDK`	| ❌                                          |

- **Standard** – GraalVM Community Edition (`graalvm-ce`).
- **JDK** – Oracle GraalVM (the successor to GraalVM Enterprise), free for production use under the [GraalVM Free Terms and Conditions](https://www.oracle.com/downloads/licenses/graal-free-license.html). It includes the advanced optimizing compiler that delivers higher peak performance than the Community Edition.
- **Enterprise** – legacy GraalVM Enterprise Edition (discontinued upstream after Java 17).

___

## Sponsor

[![playbase.pro](https://playbase.pro/storage/branding/banner.jpg)](https://playbase.pro/en)
