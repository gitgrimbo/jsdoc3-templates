A selection of custom https://github.com/jsdoc3/jsdoc templates.

To choose a custom template when using the https://github.com/phasebash/jsdoc3-maven-plugin Maven plugin.

````xml
            <!--
            https://github.com/phasebash/jsdoc3-maven-plugin
            -->
            <plugin>
                <groupId>com.github.phasebash</groupId>
                <artifactId>jsdoc3-maven-plugin</artifactId>
                <version>1.0.3-SNAPSHOT</version>
                <configuration>
                    <recursive>true</recursive>
                    <directoryRoots>
                        <directoryRoot>${basedir}/main</directoryRoot>
                    </directoryRoots>
                    <sourceFiles>
                        <sourceFile>${basedir}/index.md</sourceFile>
                    </sourceFiles>
                    <configFile>jsdoc/conf.json</configFile>
                </configuration>
                <executions>
                    <execution>
                        <goals>
                            <goal>jsdoc3</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>

````

jsdoc/conf.json (relative to pom.xml)

````json
{
    "opts": {
        "template": "jsdoc/jsdoc3-templates/my_first_template",
        "templates": {
            "default": {
                "outputSourceFiles": false,
                "outputSourceReference": false
            }
        }
    }
}
````

`outputSourceReference` is a custom option to omit the source file/lineno reference from the docs. E.g. https://github.com/gitgrimbo/jsdoc3-templates/blob/02f6a9593c901de337dffcdcfb829647f676dd27/melonjs/tmpl/details.tmpl#L65.
