# Cooking-Wizard
Ever needed some help to convert a recipe? This has the tools to help you speed up the process.

## Synopsis
Cooking Wizard is used to help halve, double, or triple the recipe as well as changing the measurements to easier to use variations for added ease

## Code example
This portion of code is how the program handles which unit of measurement to change it to.

if (mode != 0) {
            switch (type) {
                case "tsp":
                    if (newAmount >= 3) {
                        newAmount = calculator.toTbsp(newAmount, type);
                        type = "tbsp";
                    }
                    break;

                case "tbsp":
                    if (newAmount >= 4) {
                        newAmount = calculator.toCup(newAmount, type);
                        type = "cup";
                    } else if (newAmount < 1 && newAmount != 0.5) {
                        newAmount = calculator.toTsp(newAmount, type);
                        type = "tsp";
                    }
                    break;

                case "cup":
                    if (newAmount < 0.25) {
                        newAmount = calculator.toTbsp(newAmount, type);
                        type = "tbsp";
                    }
                    break;

                case "liquid cup":
                    if (newAmount >= 2) {
                        newAmount = calculator.toPt(newAmount, type);
                        type = "pt";
                        if (newAmount >= 2) {
                            newAmount = calculator.toQt(newAmount, type);
                            type = "qt";
                            if (newAmount >= 4) {
                                newAmount = calculator.toGallon(newAmount, type);
                                type  = "gal";
                            }
                        }
                    } else if (newAmount <= 0.125) {
                        newAmount = calculator.toOz(newAmount, type);
                        type = "oz";
                    }
                    break;

                case "oz":
                    if (newAmount >= 8) {
                        newAmount = calculator.toLCup(newAmount, type);
                        type = "liquid cup";
                    }
                    break;

                case "pt":
                    if (newAmount >= 2) {
                        newAmount = calculator.toQt(newAmount, type);
                        type = "qt";
                        if (newAmount >= 4) {
                            newAmount = calculator.toGallon(newAmount, type);
                            type = "gal";
                        }
                    } else if (newAmount <= 0.5) {
                        newAmount = calculator.toLCup(newAmount, type);
                        type = "Liquid cup";
                    }
                    break;
