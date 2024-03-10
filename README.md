# event_


namespace ConsoleApp1
{
    class EventClass
    {
        public event EventHandler Some;
        public void Doevent()
        {
            //EventArgs.Empty Empty : 아무 정보도 넣을 필요가 없다. 
            // 이벤트 명뒤에 ? 는 nullable를 (null)뜻한다.
            //this는 class명(Program)를 뜻한다,
            Some?.Invoke(this, EventArgs.Empty);
        }
    }
    class Program
    {
        private static void eventhandle1(object sender, EventArgs e)
        {
            Console.WriteLine("eventhandler1 call");
        }
        static void Main(string[] args)
        {
            EventClass eve = new EventClass();
            eve.Some += eventhandle1;

            eve.Doevent();           
        }
        
    }
}
