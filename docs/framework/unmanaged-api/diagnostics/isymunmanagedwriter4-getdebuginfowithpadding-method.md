---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding メソッド
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: 274bf79175bda9e880b1ef3cf8f125a017ad0734
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121670"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="1534e-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding メソッド</span><span class="sxs-lookup"><span data-stu-id="1534e-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="1534e-103">[GetDebugInfo メソッド](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)と同じように機能します。ただし、文字列データの固定サイズを `MAX_PATH`にするために、終端の null 文字の後にパス文字列がゼロで埋め込まれる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="1534e-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="1534e-104">埋め込みは、パス文字列の長さが `MAX_PATH`未満の場合にのみ指定します。</span><span class="sxs-lookup"><span data-stu-id="1534e-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="1534e-105">これにより、PE ファイルを区別するツールを簡単に記述できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1534e-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1534e-106">構文</span><span class="sxs-lookup"><span data-stu-id="1534e-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1534e-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1534e-107">Parameters</span></span>  
  
|<span data-ttu-id="1534e-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1534e-108">Parameter</span></span>|<span data-ttu-id="1534e-109">説明</span><span class="sxs-lookup"><span data-stu-id="1534e-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="1534e-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="1534e-110">Return Value</span></span>  
 <span data-ttu-id="1534e-111">`HRESULT`を返します。</span><span class="sxs-lookup"><span data-stu-id="1534e-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1534e-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="1534e-112">Requirements</span></span>  
 <span data-ttu-id="1534e-113">**ヘッダー:** CorSym .idl、CorSym .h</span><span class="sxs-lookup"><span data-stu-id="1534e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1534e-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1534e-114">See also</span></span>

- [<span data-ttu-id="1534e-115">ISymUnmanagedWriter4 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1534e-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
