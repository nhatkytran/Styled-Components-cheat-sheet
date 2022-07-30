Styled Components cheat sheet

# Basic

Import styled from ‘styled-components’;
const StyledDiv = styled.div``;

# Using props

<StyledDiv variant=”red”>Hello World</StyledDiv>

///

const StyledDiv = styled.div`color: ${(props) => (props.variant === “red” ? “red” : “green”)};`;

# Extending styles

const SuperStyledDiv = styled(SyledDiv)``

=> Polymorphic props

<SuperStyledDiv></SuperStyledDiv>
=> SuperStyledDiv inherits from StyledDiv, so SuperStyledDiv is a “div element”
=> Change SuperStyledDiv to a “a element” with “as props”
<SuperStyledDiv as=”a”></SuperStyledDiv>

# Pseudo classes

const StyledDiv = styled.div` &:hover {}`;

# Adding attributes and Passed props

1. Adding attributes

const SubmitButton = styled.button.attrs({
type: “submit”,
})``;

2. Passed props

const SubmitButton = styled.button.attrs((props) => ({
type: “submit”,
}))``;

# Animations

///

import { keyframes } from “styled-components”;

const rotate = keyframes` from {} to {}`;

const AnimatedLogo = styled.img` animation: ${rotate} infinite 2s linear;`;

# Theming

import { ThemeProvider } from “styled-components”;

const theme = {
dark: {
primary: “#000”,
text: “#fff”,
},
light: {
primary: “#fff”,
text: “#000”,
}
}

<ThemeProvider theme={theme}>
	<App />
</ThemeProvider>

///

const darkButton = styled.buttom`background-color: ${props => props.theme.dark.primary};`;

# Global Style

import { createGlobalStyle } from "styled-component";

const GobalStyle = createGlobalStyle` button {}`;

///

<ThemeProvider>
  <GlobalStyle />
  <App />
</ThemeProvider>
