---
title: GetHashFromHandle 関数
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eac353252f5a97402cbd883895b3e397c39edd6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799184"
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="c6f45-102">GetHashFromHandle 関数</span><span class="sxs-lookup"><span data-stu-id="c6f45-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="c6f45-103">指定したハッシュ アルゴリズムを使用して、指定したファイル ハンドルを含むファイルの内容に対してハッシュが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c6f45-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="c6f45-104">この関数は非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="c6f45-104">This function has been deprecated.</span></span> <span data-ttu-id="c6f45-105">代わりに[ICLRStrongName:: GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="c6f45-105">Use the [ICLRStrongName::GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f45-106">構文</span><span class="sxs-lookup"><span data-stu-id="c6f45-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6f45-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c6f45-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="c6f45-108">からハッシュされるファイルのハンドル。</span><span class="sxs-lookup"><span data-stu-id="c6f45-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="c6f45-109">[入力、出力]ハッシュアルゴリズムを指定する定数。</span><span class="sxs-lookup"><span data-stu-id="c6f45-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="c6f45-110">既定のアルゴリズムには0を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6f45-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="c6f45-111">入出力返されたハッシュバッファー。</span><span class="sxs-lookup"><span data-stu-id="c6f45-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="c6f45-112">から要求された最大`pbHash`サイズ。</span><span class="sxs-lookup"><span data-stu-id="c6f45-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="c6f45-113">入出力返さ`pbHash`れたのサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="c6f45-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6f45-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="c6f45-114">Requirements</span></span>  
 <span data-ttu-id="c6f45-115">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6f45-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6f45-116">**ヘッダー:** StrongName</span><span class="sxs-lookup"><span data-stu-id="c6f45-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c6f45-117">**ライブラリ**Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="c6f45-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6f45-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6f45-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6f45-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="c6f45-119">See also</span></span>

- [<span data-ttu-id="c6f45-120">GetHashFromHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="c6f45-120">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="c6f45-121">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c6f45-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
