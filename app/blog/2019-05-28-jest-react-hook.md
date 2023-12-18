---
slug: jest-react-hook
title: Test React Hook
authors:
  name: Carlos Gonzalez
tags: [react, jest, testing]
---


```js title="useAdvise.test.ts"
import { renderHook } from '@testing-library/react-hooks';
import { useAdvice } from 'hooks/useAdvice';

describe('useAdviser', () => {
  it(
    'return clients when load',
    () => {
      const { result } = renderHook(() => useAdvice());

      expect(result.current.clients).toEqual([]);
    },
  );
});

```
