import React, { useState, useRef, useEffect } from 'react';
import { Send, Sparkles, Menu, Plus, MessageSquare } from 'lucide-react';

export default function Genisi() {
  const [messages, setMessages] = useState([]);
  const [input, setInput] = useState('');
  const [loading, setLoading] = useState(false);
  const [sidebarOpen, setSidebarOpen] = useState(false);
  const messagesEndRef = useRef(null);

  const scrollToBottom = () => {
    messagesEndRef.current?.scrollIntoView({ behavior: 'smooth' });
  };

  useEffect(() => {
    scrollToBottom();
  }, [messages]);

  const handleSubmit = async () => {
    if (!input.trim() || loading) return;

    const userMessage = input.trim();
    setInput('');
    setMessages(prev => [...prev, { role: 'user', content: userMessage }]);
    setLoading(true);

    try {
      const response = await fetch('https://api.anthropic.com/v1/messages', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          model: 'claude-sonnet-4-20250514',
          max_tokens: 1000,
          messages: [
            ...messages.filter(m => m.role !== 'system'),
            { role: 'user', content: userMessage }
          ].map(m => ({ role: m.role, content: m.content }))
        })
      });

      const data = await response.json();
      const assistantMessage = data.content
        .filter(item => item.type === 'text')
        .map(item => item.text)
        .join('\n');

      setMessages(prev => [...prev, { 
        role: 'assistant', 
        content: assistantMessage || 'عذراً، حدث خطأ في الاتصال.' 
      }]);
    } catch (error) {
      setMessages(prev => [...prev, { 
        role: 'assistant', 
        content: 'عذراً، لم أستطع الاتصال بالخدمة. يرجى التأكد من إعداد API بشكل صحيح.' 
      }]);
    } finally {
      setLoading(false);
    }
  };

  const handleKeyPress = (e) => {
    if (e.key === 'Enter' && !e.shiftKey) {
      e.preventDefault();
      handleSubmit();
    }
  };

  const newChat = () => {
    setMessages([]);
  };

  const suggestions = [
    "اكتب لي قصة قصيرة",
    "ساعدني في تعلم البرمجة",
    "اشرح لي الذكاء الاصطناعي",
    "اقترح أفكار إبداعية"
  ];

  return (
    <div className="flex h-screen bg-black text-white">
      {/* Sidebar */}
      <div className={`${sidebarOpen ? 'w-72' : 'w-0'} transition-all duration-300 bg-zinc-950 border-r border-zinc-800 overflow-hidden flex flex-col`}>
        <div className="p-4">
          <button
            onClick={newChat}
            className="w-full flex items-center gap-3 px-4 py-3 rounded-xl bg-zinc-900 hover:bg-zinc-800 transition-all"
          >
            <Plus className="w-5 h-5" />
            <span className="font-medium">محادثة جديدة</span>
          </button>
        </div>
        
        <div className="flex-1 overflow-y-auto px-4">
          <div className="space-y-2">
            <div className="text-xs text-zinc-500 px-2 mb-2">المحادثات السابقة</div>
            {[1, 2, 3].map((i) => (
              <button
                key={i}
                className="w-full flex items-center gap-3 px-3 py-2 rounded-lg hover:bg-zinc-900 transition-all text-right"
              >
                <MessageSquare className="w-4 h-4 text-zinc-500" />
                <span className="text-sm text-zinc-400 truncate">محادثة سابقة {i}</span>
              </button>
            ))}
          </div>
        </div>

        <div className="p-4 border-t border-zinc-800">
          <div className="text-xs text-zinc-600">
            Genisi AI Assistant
          </div>
        </div>
      </div>

      {/* Main Area */}
      <div className="flex-1 flex flex-col">
        {/* Header */}
        <div className="h-16 border-b border-zinc-800 flex items-center px-6 gap-4">
          <button
            onClick={() => setSidebarOpen(!sidebarOpen)}
            className="p-2 rounded-lg hover:bg-zinc-900 transition-all"
          >
            <Menu className="w-5 h-5" />
          </button>
          
          <div className="flex items-center gap-3">
            <div className="w-8 h-8 rounded-full bg-gradient-to-r from-blue-500 via-purple-500 to-pink-500 flex items-center justify-center">
              <Sparkles className="w-4 h-4 text-white" />
            </div>
            <div>
              <h1 className="text-lg font-semibold">Genisi</h1>
            </div>
          </div>
        </div>

        {/* Messages Area */}
        <div className="flex-1 overflow-y-auto">
          {messages.length === 0 ? (
            <div className="h-full flex flex-col items-center justify-center px-6 max-w-4xl mx-auto">
              <div className="w-20 h-20 rounded-full bg-gradient-to-r from-blue-500 via-purple-500 to-pink-500 flex items-center justify-center mb-6">
                <Sparkles className="w-10 h-10 text-white" />
              </div>
              <h1 className="text-5xl font-medium mb-2 bg-gradient-to-r from-blue-400 via-purple-400 to-pink-400 bg-clip-text text-transparent">
                مرحباً، أنا Genisi
              </h1>
              <p className="text-zinc-500 text-lg mb-12">كيف يمكنني مساعدتك اليوم؟</p>
              
              <div className="grid grid-cols-2 gap-4 w-full max-w-3xl">
                {suggestions.map((suggestion, index) => (
                  <button
                    key={index}
                    onClick={() => setInput(suggestion)}
                    className="p-4 rounded-2xl bg-zinc-900 hover:bg-zinc-800 border border-zinc-800 text-right transition-all group"
                  >
                    <div className="text-sm text-zinc-300 group-hover:text-white transition-colors">
                      {suggestion}
                    </div>
                  </button>
                ))}
              </div>
            </div>
          ) : (
            <div className="px-6 py-8 space-y-8 max-w-4xl mx-auto">
              {messages.map((message, index) => (
                <div key={index} className="space-y-2">
                  <div className="flex items-center gap-3 mb-3">
                    {message.role === 'user' ? (
                      <>
                        <div className="w-8 h-8 rounded-full bg-gradient-to-r from-emerald-500 to-teal-500 flex items-center justify-center">
                          <span className="text-white text-sm font-bold">أنت</span>
                        </div>
                        <span className="text-sm text-zinc-400">أنت</span>
                      </>
                    ) : (
                      <>
                        <div className="w-8 h-8 rounded-full bg-gradient-to-r from-blue-500 via-purple-500 to-pink-500 flex items-center justify-center">
                          <Sparkles className="w-4 h-4 text-white" />
                        </div>
                        <span className="text-sm text-zinc-400">Genisi</span>
                      </>
                    )}
                  </div>
                  <div className={`text-base leading-relaxed ${message.role === 'user' ? 'text-zinc-200' : 'text-zinc-100'}`}>
                    {message.content}
                  </div>
                </div>
              ))}
              
              {loading && (
                <div className="space-y-2">
                  <div className="flex items-center gap-3 mb-3">
                    <div className="w-8 h-8 rounded-full bg-gradient-to-r from-blue-500 via-purple-500 to-pink-500 flex items-center justify-center">
                      <Sparkles className="w-4 h-4 text-white" />
                    </div>
                    <span className="text-sm text-zinc-400">Genisi</span>
                  </div>
                  <div className="flex gap-2">
                    <div className="w-2 h-2 bg-zinc-600 rounded-full animate-bounce" style={{ animationDelay: '0ms' }} />
                    <div className="w-2 h-2 bg-zinc-600 rounded-full animate-bounce" style={{ animationDelay: '150ms' }} />
                    <div className="w-2 h-2 bg-zinc-600 rounded-full animate-bounce" style={{ animationDelay: '300ms' }} />
                  </div>
                </div>
              )}
              <div ref={messagesEndRef} />
            </div>
          )}
        </div>

        {/* Input Area */}
        <div className="border-t border-zinc-800 p-4">
          <div className="max-w-4xl mx-auto">
            <div className="relative flex items-end gap-3 bg-zinc-900 rounded-3xl p-2 border border-zinc-800 focus-within:border-zinc-700 transition-all">
              <input
                type="text"
                value={input}
                onChange={(e) => setInput(e.target.value)}
                onKeyPress={handleKeyPress}
                placeholder="اكتب رسالة إلى Genisi..."
                className="flex-1 bg-transparent px-4 py-3 text-white placeholder-zinc-500 focus:outline-none resize-none"
                disabled={loading}
              />
              <button
                onClick={handleSubmit}
                disabled={loading || !input.trim()}
                className="p-3 rounded-2xl bg-white hover:bg-zinc-200 disabled:opacity-30 disabled:cursor-not-allowed transition-all flex-shrink-0"
              >
                <Send className="w-5 h-5 text-black" />
              </button>
            </div>
            <div className="text-xs text-zinc-600 text-center mt-3">
              Genisi يمكن أن يرتكب أخطاء. يرجى التحقق من المعلومات المهمة.
            </div>
          </div>
        </div>
      </div>
    </div>
  );
}
