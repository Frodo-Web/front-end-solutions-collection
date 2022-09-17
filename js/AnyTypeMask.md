````JavaScript
function numericStringMask(str, mask) {
  if (!mask) return str;

  const numeric = str.replaceAll(/[^\d]/g, '');

  let idx = 0;

  const formated = mask.split('').map(el => {
    if (el === '#') {
      el = numeric[idx];
      idx++;
    }
    return el;
  });

  return formated.join('');
}



Example 1: (123) 456 - 7890

numericStringMask('1234567890', '(###) ### - ####')

Example 2: (123) 456-7890

numericStringMask('1234567890', '(###) ###-####')

Example 3: (11) 90056-7890

numericStringMask('11900567890', '(##) #####-####')
}
