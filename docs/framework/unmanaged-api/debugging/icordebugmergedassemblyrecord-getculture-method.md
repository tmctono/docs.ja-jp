---
title: ICorDebugMergedAssemblyRecord::GetCulture メソッド
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: f73aac169cc048a87aca3bfc325cf8c6243012e9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207864"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="e76cd-102">ICorDebugMergedAssemblyRecord::GetCulture メソッド</span><span class="sxs-lookup"><span data-stu-id="e76cd-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="e76cd-103">アセンブリのカルチャ名文字列を取得します。</span><span class="sxs-lookup"><span data-stu-id="e76cd-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e76cd-104">構文</span><span class="sxs-lookup"><span data-stu-id="e76cd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,
   [out] ULONG32 *pcchCulture,
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e76cd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e76cd-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="e76cd-106">[in] `szCulture` バッファー内の文字数。</span><span class="sxs-lookup"><span data-stu-id="e76cd-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="e76cd-107">[out] `szCulture` バッファーに実際に書き込まれた文字数。</span><span class="sxs-lookup"><span data-stu-id="e76cd-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="e76cd-108">[out] カルチャ名を格納する文字配列。</span><span class="sxs-lookup"><span data-stu-id="e76cd-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e76cd-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="e76cd-109">Remarks</span></span>  
 <span data-ttu-id="e76cd-110">カルチャ名は、"en-US" (英語 (米国) カルチャ)、"neutral" (ニュートラル カルチャ) など、カルチャを識別する一意の文字列です。</span><span class="sxs-lookup"><span data-stu-id="e76cd-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e76cd-111">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e76cd-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e76cd-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="e76cd-112">Requirements</span></span>  
 <span data-ttu-id="e76cd-113">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e76cd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e76cd-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e76cd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e76cd-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e76cd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e76cd-116">**.NET Framework のバージョン:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e76cd-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e76cd-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e76cd-117">See also</span></span>

- [<span data-ttu-id="e76cd-118">ICorDebugMergedAssemblyRecord インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e76cd-118">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="e76cd-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="e76cd-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
