---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: cd634b4d4a88d83d425b787ed8493f9aa2504988
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053417"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="a8b2e-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="a8b2e-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="a8b2e-103">同じリストを反復処理するため、現在の列挙子と同じ状態の別の未加工入力デバイスの列挙子を作成します。</span><span class="sxs-lookup"><span data-stu-id="a8b2e-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8b2e-104">構文</span><span class="sxs-lookup"><span data-stu-id="a8b2e-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8b2e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a8b2e-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="a8b2e-106">入出力[IEnumRAWINPUTDEVICE](ienumrawinputdevice.md)インターフェイスポインターを受け取る出力変数のアドレス。</span><span class="sxs-lookup"><span data-stu-id="a8b2e-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="a8b2e-107">メソッドが失敗した場合、この出力変数の値は未定義になります。</span><span class="sxs-lookup"><span data-stu-id="a8b2e-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a8b2e-108">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="a8b2e-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="a8b2e-109">HRESULT:このメソッドは、標準の戻り値 E_INVALIDARG、E_OUTOFMEMORY、および E_UNEXPECTED をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a8b2e-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8b2e-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="a8b2e-110">Remarks</span></span>  
 <span data-ttu-id="a8b2e-111">このメソッドを使用すると、後でその点に戻るために、列挙シーケンス内のポイントを記録できます。</span><span class="sxs-lookup"><span data-stu-id="a8b2e-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="a8b2e-112">呼び出し元は、最初の列挙子とは別に、この新しい列挙子を解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8b2e-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
