---
title: '軽減策: WPF ウィンドウのレンダリング'
description: Windows 8 以降で実行されている .NET Framework 4.6 の WPF ウィンドウ レンダリングの影響と軽減策について説明します。
ms.date: 03/30/2017
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
ms.openlocfilehash: d624478d17a4076107438f71b0a86eeb6d9f3ea4
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475334"
---
# <a name="mitigation-wpf-window-rendering"></a>軽減策:WPF ウィンドウのレンダリング

Windows 8 以上で実行している .NET Framework 4.6 では、マルチ モニターのシナリオで 1 つのディスプレイの外部にウィンドウを拡張すると、ウィンドウ全体がクリッピングなしでレンダリングされます。

## <a name="impact"></a>影響

一般に、複数のモニターで、クリッピングなしでウィンドウ全体を表示することが期待の動作です。 ただし、Windows 7 以前のバージョンでは、2 つ目のモニターにウィンドウの一部をレンダリングするとパフォーマンスに大きな影響があるため、WPF ウィンドウが 1 つのディスプレイの外部に拡張されるときにはクリッピングされます。

Windows 8 以上で複数のモニターに WPF ウィンドウをレンダリングする際の詳細な影響は、多数の要因に依存しているために、正確に数量化することはできません。 場合によっては、グラフィックを多用するアプリケーションを実行するユーザーや複数のモニターに及ぶウィンドウを使用するユーザーの場合は特に、依然としてパフォーマンスに望ましくない影響が生じることがあります。 または、.NET Framework の複数のバージョン間で一貫性のある動作が実現できれば十分な場合もあります 。

## <a name="mitigation"></a>軽減策

この変更を無効にして、WPF ウィンドウが 1 つのディスプレイを超える場合にクリッピングされるという、以前の動作に戻すこともできます。 これには、2 つの方法があります。

- `<EnableMultiMonitorDisplayClipping>` 要素をアプリケーションの構成ファイルの `<appSettings>` セクションに追加することにより、Windows 8 以降で実行中のアプリケーションでこの動作を無効にしたり有効にしたりすることができます。 たとえば、次の構成セクションにより、クリッピングなしのレンダリングが無効になります。

  ```xml
  <appSettings>
      <add key="EnableMultiMonitorDisplayClipping" value="true"/>
    </appSettings>
  ```

  `<EnableMultiMonitorDisplayClipping>` 構成設定には、次の 2 つの値のいずれかを指定できます。

  - `true` を指定すると、レンダリングの際にウィンドウをモニターの境界でクリッピングすることを有効にします。

  - `false` を指定すると、レンダリングの際にウィンドウをモニターの境界でクリッピングすることを無効にします。

- これを行うには、アプリの起動時に <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> プロパティを `true` に設定します。

## <a name="see-also"></a>関連項目

- [アプリケーションの互換性](application-compatibility.md)
